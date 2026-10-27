---
description: >-
  This chapter explains how an external system calls an Agent, and covers
  permission checks, continuing a conversation, handling attachments, managing
  data and troubleshooting. It is organized around pr
---

# Agent API Integration

This manual covers the full Agent API integration flow, so that an external system can call an Agent through the OpenAI-compatible API, continue a conversation, send files, and query or manage conversation records.

It is written for:

* Developers integrating an Agent into an existing product or enterprise system
* People responsible for API integration testing, acceptance and operations
* System administrators who need to confirm how Agent permissions, files and conversation data are handled

If this is your first integration, we recommend completing one minimal request as described in "Quick start", then adding conversation continuation, files and retry handling as needed.

> In this manual, `assistant id` is the product's Agent ID, and `thread_id` corresponds to the system's internal session.

## Before you start

### Information you need

Before you start, get the following from your system administrator:

| Item         | Description                                     | Example          |
| ------------ | ----------------------------------------------- | ---------------- |
| Host address | The environment where the Agent API is deployed | `https://{host}` |
| API Key      | The access credential used to call the API      | `ask_xxx`        |
| Agent ID     | The identifier of the Agent to call             | `xxx`            |
| User ID      | Used when calling on behalf of a specified user | `user-001`       |

Keep the API Key safe: never put it in front-end code, public documents or public code repositories.

### Confirming the Base URL

This manual uses `/v1` for the path prefix of the OpenAI-compatible API. The actual URL is usually:

```
https://{host}/openai/v1
```

For example, the full path for Chat Completions is:

```
https://{host}/openai/v1/chat/completions
```

Always confirm the full path against the configuration of your deployment.

### Authentication

All `/v1/*` endpoints use a Bearer token. Add this to the request header:

```http
Authorization: Bearer <api_key_plain>
```

Common authentication errors:

| HTTP status | Error code         | Cause                                                           |
| ----------- | ------------------ | --------------------------------------------------------------- |
| 401         | `invalid_header`   | The `Authorization` header is missing, or is not a Bearer token |
| 401         | `invalid_api_key`  | The API Key is invalid                                          |
| 403         | `api_key_disabled` | The API Key has been disabled                                   |

### Supported APIs

<table data-search="false"><thead><tr><th>Function</th><th>Method</th><th>Endpoint</th></tr></thead><tbody><tr><td>Check Agent permissions</td><td>GET</td><td><code>/api/public/assistant/permissions/check</code></td></tr><tr><td>Call an Agent</td><td>POST</td><td><code>/v1/chat/completions</code></td></tr><tr><td>List conversations</td><td>GET</td><td><code>/v1/threads</code></td></tr><tr><td>List conversation messages</td><td>GET</td><td><code>/v1/threads/{thread_id}/messages</code></td></tr><tr><td>Delete a conversation</td><td>DELETE</td><td><code>/v1/threads/{thread_id}</code></td></tr><tr><td>Upload a file</td><td>POST</td><td><code>/v1/files</code></td></tr><tr><td>List files</td><td>GET</td><td><code>/v1/files</code></td></tr><tr><td>Get a single file</td><td>GET</td><td><code>/v1/files/{file_id}</code></td></tr><tr><td>Delete a file</td><td>DELETE</td><td><code>/v1/files/{file_id}</code></td></tr></tbody></table>

## Quick start: your first Agent conversation

For a first integration, complete these three steps in order:

1. Confirm the API Key, Agent ID and permissions.
2. Send a minimal Chat Completions request.
3. Check the response and save the `thread_id`.

### Checking whether a user has Agent permission

If the external system calls the Agent on behalf of a real user, check first whether that user has permission to use the Agent.

Endpoint:

```http
GET /api/public/assistant/permissions/check
```

Query parameters:

| Parameter     | Required | Description |
| ------------- | -------- | ----------- |
| `userId`      | Yes      | User ID     |
| `assistantId` | Yes      | Agent ID    |

Example request:

```
https://{host}/api/public/assistant/permissions/check?userId=user-001&assistantId=xxx
```

With permission, `hasPermission` returns `true`:

```json
{
  "resultSet": {
    "hasPermission": true,
    "acl": ["READ"],
    "message": "Permission granted."
  }
}
```

Without permission, `hasPermission` returns `false`:

```json
{
  "resultSet": {
    "hasPermission": false,
    "acl": [],
    "message": "Permission denied."
  }
}
```

If `userId` or `assistantId` is missing, the system may still return HTTP 200, with a body indicating no permission:

```json
{
  "resultSet": {
    "hasPermission": false,
    "acl": [],
    "message": "Missing userId or assistantId."
  }
}
```

So use `resultSet.hasPermission` to decide whether to continue, rather than the HTTP status code alone.

### Sending your first message

Endpoint:

```http
POST /v1/chat/completions
```

Headers:

```http
Content-Type: application/json
Authorization: Bearer <api_key_plain>
```

A minimal working request:

```bash
curl -X POST "https://{host}/openai/v1/chat/completions" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer ask_xxx" \
  -d '{
    "model": "xxx",
    "messages": [
      {
        "role": "user",
        "content": "Hello"
      }
    ],
    "stream": false
  }'
```

In this API, `model` is the Agent ID to call. Two formats are supported:

```
xxx
assistant:xxx
```

We recommend using the Agent ID without a prefix:

```json
{
  "model": "xxx"
}
```

### Checking the response and saving thread\_id

On success, the system returns the Agent's answer and the `thread_id` of this conversation:

```json
{
  "id": "chatcmpl-xxx",
  "object": "chat.completion",
  "created": 1710000000,
  "model": "xxx",
  "thread_id": "thread-abc123",
  "choices": [
    {
      "index": 0,
      "message": {
        "role": "assistant",
        "content": "..."
      },
      "text": "...",
      "finish_reason": "stop"
    }
  ],
  "usage": {
    "prompt_tokens": 123,
    "completion_tokens": 45,
    "total_tokens": 168
  }
}
```

When integrating, confirm that:

* `choices[0].message.content` contains the Agent's answer
* `thread_id` was returned
* You have saved this `thread_id` if you need to continue the conversation later

We recommend storing the `thread_id` exactly as the API returns it, without removing or adding the `thread-` prefix yourself.

## Sending messages and continuing a conversation

### The basic Messages format

`messages` is an array of messages. The most basic text message looks like this:

```json
{
  "role": "user",
  "content": "Please summarize this document"
}
```

`content` can also be an array:

```json
{
  "role": "user",
  "content": [
    {
      "type": "text",
      "text": "Please analyze the attachment"
    }
  ]
}
```

Supported `content` formats:

* String: converted into a single `text` item
* Array: can hold both text and files
* Object: converted into a single-element array

### How messages are processed

The system currently uses the last message with `role` set to `user` as the main text input.

If that message's `content` is an array, all items of `type` `text` are joined with line breaks. Earlier messages are not fully rebuilt into the Agent's internal workflow history.

So when integrating:

* Put the question you actually want the Agent to answer in the last user message.
* Use the same `thread_id` when you need to keep the context.
* Do not rely on resending the full message history to continue a conversation.

### Continuing the same conversation

After a successful first call, pass the `thread_id` from the response in the next request:

```json
{
  "model": "xxx",
  "thread_id": "thread-abc123",
  "messages": [
    {
      "role": "user",
      "content": "Now turn the previous answer into a table"
    }
  ]
}
```

`thread_id` supports these formats:

```
thread-<sessionId>
<sessionId>
```

To avoid conversion errors, use the value the previous API call returned.

### Running on behalf of a specified user

To run with a specific user's permissions, include:

```json
{
  "metadata": {
    "user_id": "user-001"
  }
}
```

Before using `metadata.user_id`, call the permission check API to confirm that the user has permission to use the Agent.

## Passing files to an Agent

There are two ways to pass a file to an Agent:

| Method                                          | When to use it                                                    |
| ----------------------------------------------- | ----------------------------------------------------------------- |
| Upload the file first, then reference `file_id` | The same file is reused, or you need to manage files separately   |
| Send `file_data` directly in the chat request   | The file is used once, and the external system can produce Base64 |

### Method one

#### Upload the file first

Endpoint:

```http
POST /v1/files
```

Content-Type:

```http
multipart/form-data
```

Form fields:

| Field     | Type    | Required | Default      | Description               |
| --------- | ------- | -------- | ------------ | ------------------------- |
| `file`    | file    | Yes      | -            | The file to upload        |
| `purpose` | string  | No       | `assistants` | The file's purpose        |
| `is_temp` | boolean | No       | `false`      | Whether it is a temp file |

Example request:

```bash
curl -X POST "https://{host}/openai/v1/files" \
  -H "Authorization: Bearer ask_xxx" \
  -F "file=@demo.pdf" \
  -F "purpose=assistants" \
  -F "is_temp=false"
```

Successful response:

```json
{
  "id": "file-abc123",
  "object": "file",
  "bytes": 123,
  "created_at": 1735280000,
  "filename": "demo.pdf",
  "purpose": "assistants",
  "status": "uploaded"
}
```

Once a file is uploaded, the system binds it to the API Key. Save the `id` from the response for use in later chat requests.

#### Referencing an existing file\_id in a chat request

Put the text and the file in the same `content` array:

```json
{
  "model": "xxx",
  "messages": [
    {
      "role": "user",
      "content": [
        {
          "type": "text",
          "text": "Please summarize the attachment"
        },
        {
          "type": "file",
          "file": {
            "filename": "demo.pdf",
            "file_id": "file-abc123"
          }
        }
      ]
    }
  ]
}
```

`file_id` supports both `file-xxx` and the form without the `file-` prefix. We recommend using the value the file upload API returned.

### Method two

#### Sending file\_data directly

`file_data` accepts Base64 or a data URI:

```json
{
  "model": "xxx",
  "messages": [
    {
      "role": "user",
      "content": [
        {
          "type": "text",
          "text": "Please analyze this document"
        },
        {
          "type": "file",
          "file": {
            "filename": "demo.txt",
            "file_data": "data:text/plain;base64,SGVsbG8="
          }
        }
      ]
    }
  ]
}
```

With a data URI, the system takes the string after `base64,` and decodes it. Once decoded, the file goes through the normal upload flow and is bound to the API Key.

### File permissions and security limits

Before passing a file into the Agent workflow, the system confirms that the file is bound to the API Key used for the call.

Only files that pass this check are passed into the workflow. If no file passes, the `fileIds` sent is `null`.

If the file does not exist, or does not belong to the current API Key, the system returns 404:

```json
{
  "error": {
    "message": "File not found.",
    "type": "invalid_request_error",
    "code": "not_found"
  }
}
```

## Managing files

### Listing files

```http
GET /v1/files
```

Response format:

```json
{
  "object": "list",
  "data": []
}
```

### Getting a single file

```http
GET /v1/files/{file_id}
```

`file_id` supports these formats:

```
file-<id>
<id>
```

### Deleting a file

```http
DELETE /v1/files/{file_id}
```

Successful response:

```json
{
  "id": "file-abc123",
  "object": "file",
  "deleted": true
}
```

Before deleting a file, check whether another process or external system still shares it, so you do not break existing functionality.

## Querying and managing conversations

### Listing conversations

Endpoint:

```http
GET /v1/threads
```

Query parameters:

| Parameter | Type    | Default | Description       |
| --------- | ------- | ------- | ----------------- |
| `limit`   | integer | 50      | Number of records |
| `order`   | string  | `desc`  | Sort direction    |

Example response:

```json
{
  "object": "list",
  "data": [
    {
      "id": "thread-<sessionId>",
      "object": "thread",
      "created_at": 1735280000,
      "metadata": {},
      "tool_resources": {}
    }
  ]
}
```

> The `order` parameter does not currently change the sort order, so integrations should not rely on it alone to determine the order of the data.

### Listing conversation messages

Endpoint:

```http
GET /v1/threads/{thread_id}/messages
```

Query parameters:

| Parameter | Type    | Default | Description                               |
| --------- | ------- | ------- | ----------------------------------------- |
| `order`   | string  | `asc`   | Sort direction                            |
| `limit`   | integer | 50      | Number of records                         |
| `after`   | string  | -       | Kept for compatibility; not yet in effect |
| `before`  | string  | -       | Kept for compatibility; not yet in effect |

Example response:

```json
{
  "object": "list",
  "data": [
    {
      "id": "<messageId>",
      "object": "thread.message",
      "created_at": 1735280000,
      "role": "user",
      "content": [
        {
          "type": "text",
          "text": {
            "value": "..."
          }
        }
      ],
      "thread_id": "thread-<sessionId>"
    }
  ]
}
```

### Deleting a conversation

```http
DELETE /v1/threads/{thread_id}
```

Successful response:

```json
{
  "deleted": true,
  "thread_id": "thread-<sessionId>"
}
```

## Streaming responses

The Chat Completions request body has a `stream` field:

```json
{
  "stream": true
}
```

The specifications currently describe streaming behavior inconsistently:

* One says the controller always returns JSON, but still passes `stream` through to the service.
* Another says that with `stream=true` it uses `text/event-stream` and sends chunks and `[DONE]` over SSE.

So before adopting token-by-token display or SSE handling, confirm whether streaming is enabled in your deployment. Until you have, use:

```json
{
  "stream": false
}
```

## Rate limits and retries

### Checking your remaining quota

On a successful `POST /v1/chat/completions`, the response headers usually include:

```
X-RateLimit-Limit-Requests
X-RateLimit-Remaining-Requests
X-RateLimit-Reset-Requests
```

When the limit is exceeded, the system returns HTTP 429 with:

```
X-RateLimit-Limit-Requests
X-RateLimit-Remaining-Requests: 0
X-RateLimit-Reset-Requests
Retry-After
```

Example error response:

```json
{
  "error": {
    "message": "Rate limit exceeded. Please retry after <N> seconds.",
    "type": "rate_limit_error",
    "code": "rate_limit_exceeded"
  }
}
```

### Recommended retry policy

| Status code | What to do                                                                                       |
| ----------- | ------------------------------------------------------------------------------------------------ |
| 401, 403    | Do not retry automatically; check the API Key, the Bearer format and whether the key is disabled |
| 404         | Do not retry directly; check the `thread_id`, `file_id` and their API Key ownership              |
| 422         | Do not retry directly; fix the missing or malformed request body                                 |
| 429         | Wait as indicated by `Retry-After`, then retry                                                   |
| 500         | Retry a limited number of times depending on the error, and keep the error record                |
| 503, 504    | Use a limited number of delayed retries with backoff                                             |

Avoid unlimited or immediate consecutive retries, which add load to the service. If retries keep failing, stop the process and record a request summary with sensitive information removed, plus the status code, error code and time, for later investigation.

## Common errors and how to resolve them

<table data-search="false"><thead><tr><th>HTTP</th><th>type</th><th>code</th><th>Cause and what to do</th></tr></thead><tbody><tr><td>401</td><td><code>invalid_request_error</code></td><td><code>invalid_header</code></td><td>Check that the <code>Authorization</code> header is present and in the form <code>Bearer &#x3C;API Key></code></td></tr><tr><td>401</td><td><code>invalid_request_error</code></td><td><code>invalid_api_key</code></td><td>Confirm the API Key is correct</td></tr><tr><td>403</td><td><code>invalid_request_error</code></td><td><code>api_key_disabled</code></td><td>Contact your administrator to check the API Key's status</td></tr><tr><td>404</td><td><code>invalid_request_error</code></td><td><code>not_found</code></td><td>Confirm the thread or file exists and belongs to the current API Key</td></tr><tr><td>422</td><td><code>invalid_request_error</code></td><td><code>invalid_request</code></td><td>Check required fields such as <code>model</code> and the data format</td></tr><tr><td>429</td><td><code>rate_limit_error</code></td><td><code>rate_limit_exceeded</code></td><td>Wait as indicated by <code>Retry-After</code>, then retry</td></tr><tr><td>429</td><td><code>rate_limit_error</code></td><td><code>controller_throttle</code></td><td>The service is busy; retry later</td></tr><tr><td>429</td><td><code>rate_limit_error</code></td><td><code>chat_throttle_timeout</code></td><td>Timed out waiting for an available processing slot; retry later</td></tr><tr><td>500</td><td><code>server_error</code></td><td><code>workflow_failed</code></td><td>The Agent workflow failed</td></tr><tr><td>500</td><td><code>server_error</code></td><td><code>cancelled</code></td><td>The job was canceled</td></tr><tr><td>500</td><td><code>server_error</code></td><td><code>chat_failed</code></td><td>The chat run failed</td></tr><tr><td>503</td><td><code>server_error</code></td><td><code>database_busy</code></td><td>Database connection usage is too high or saturated</td></tr><tr><td>503</td><td><code>server_error</code></td><td><code>database_unavailable</code></td><td>The database is temporarily unreachable</td></tr><tr><td>503</td><td><code>server_error</code></td><td><code>chat_interrupted</code></td><td>Interrupted while waiting for an available processing slot</td></tr><tr><td>504</td><td><code>server_error</code></td><td><code>database_timeout</code></td><td>The database query timed out</td></tr><tr><td>504</td><td><code>server_error</code></td><td><code>timeout</code></td><td>The request timed out</td></tr></tbody></table>

Some error codes appear only in individual specifications, and it is not yet confirmed whether they are implemented in the current version:

```
api_key_expired
assistant_disabled
assistant_permission_denied
budget_exceeded
guardrails_blocked
streaming_unavailable
```

Until that is confirmed, do not build core logic around these error codes alone.

## Request and response field reference

### Chat Completions request body

| Field              | Type    | Required | Description                                                             |
| ------------------ | ------- | -------- | ----------------------------------------------------------------------- |
| `model`            | string  | Yes      | The Agent ID; the `assistant:` prefix is supported                      |
| `messages`         | array   | Yes      | The messages being sent                                                 |
| `thread_id`        | string  | No       | The conversation or session ID; the `thread-` prefix is supported       |
| `stream`           | boolean | No       | Whether to stream; confirm your environment supports it first           |
| `tools`            | array   | No       | Kept for compatibility only; not recommended as a production capability |
| `metadata.user_id` | string  | No       | Used to run with a specified user's permissions                         |

### Chat Completions response

<table data-search="false"><thead><tr><th>Field</th><th>Type</th><th>Description</th></tr></thead><tbody><tr><td><code>id</code></td><td>string</td><td>The response ID, in the form <code>chatcmpl-...</code></td></tr><tr><td><code>object</code></td><td>string</td><td>Always <code>chat.completion</code></td></tr><tr><td><code>created</code></td><td>number</td><td>Creation time, in epoch seconds</td></tr><tr><td><code>model</code></td><td>string</td><td>The request's <code>model</code>, returned as is</td></tr><tr><td><code>thread_id</code></td><td>string</td><td>This conversation's ID, in the form <code>thread-...</code></td></tr><tr><td><code>choices</code></td><td>array</td><td>The results; currently always one choice</td></tr><tr><td><code>usage</code></td><td>object</td><td>Token statistics; returned when the system can obtain them</td></tr></tbody></table>

`choices[0]` fields:

| Field             | Description                                                         |
| ----------------- | ------------------------------------------------------------------- |
| `message.role`    | Always `assistant`                                                  |
| `message.content` | The Agent's response text                                           |
| `text`            | The same as `message.content`, for compatibility with older clients |
| `finish_reason`   | Always `stop`                                                       |

## Known limitations

Note the following before integrating:

* The `tools` field is kept for interface compatibility only and is not recommended as a production capability.
* Earlier messages are not fully mapped into the Agent's internal workflow history.
* Use the same `thread_id` to continue a conversation.
* The `order` parameter of `GET /v1/threads` does not currently change the sort order.
* The `after` and `before` parameters of `GET /v1/threads/{thread_id}/messages` are kept for compatibility but are not yet in effect.
* Files are checked for API Key binding before being passed into a workflow.
* For shared files, the external system has to assess the impact before deleting them.
* The documentation on streaming behavior is currently inconsistent, so confirm your deployment before adopting it.

## Integration acceptance checklist

Before going live, confirm the following in order:

* You have the correct host address, API Key and Agent ID.
* The API Key passes Bearer token authentication.
* If running on behalf of a specified user, the Agent permission check is in place.
* A minimal chat request with `stream=false` succeeded.
* `choices[0].message.content` is read correctly.
* The `thread_id` returned by the API is saved.
* Continuing a conversation with the same `thread_id` has been verified.
* If you need attachments, file upload, `file_id` references and API Key binding have been verified.
* Limited retries with backoff are in place for 429, 503 and 504.
* The necessary error records and tracing information are kept.
* If you need SSE, you have confirmed that your environment supports `stream=true`.
* You have confirmed that deleting a thread or file does not affect other processes in use.

## FAQ

<details>

<summary>Why does the API return 401?</summary>

Check that the request header includes:

```http
Authorization: Bearer <api_key_plain>
```

If the format is correct, confirm that the API Key is valid.

</details>

<details>

<summary>Why does the permission check return HTTP 200 but the Agent still cannot be used?</summary>

The permission check API may return HTTP 200 even when a parameter is missing or there is no permission. Use the value of `resultSet.hasPermission` to decide.

</details>

<details>

<summary>Why doesn't the Agent keep the context when I pass the full messages array?</summary>

The system currently uses the last user message as the main input, and earlier messages are not fully rebuilt into the workflow history. Save and pass the same `thread_id` to continue the conversation.

</details>

<details>

<summary>Why didn't the Agent read the attachment?</summary>

Check that:

1. The `file_id` is correct.
2. The file was uploaded with the API Key you are using.
3. The file item in `content` uses `type: "file"`.
4. `file_data` is valid Base64 or a valid data URI.

</details>

<details>

<summary>How long should I wait before retrying after a 429?</summary>

Read `Retry-After` from the response headers and wait that long before retrying.

</details>

<details>

<summary>Can I just turn on stream=true?</summary>

The specifications currently describe streaming support inconsistently. Before using it, confirm with your system administrator whether your deployment supports SSE. Until then, use `stream=false`.

</details>
