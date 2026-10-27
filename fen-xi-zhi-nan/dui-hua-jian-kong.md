---
description: >-
  Conversation monitoring lists the messages of all Agents in one place, helping
  admins find the conversations that need attention by source and abnormal
  event, and view the full conversation.
---

# Conversation

The **Conversation** page (conversation monitoring) lists every message received by all Agents, one row per message. Admins can filter by source, Agent or event to quickly find conversations that failed or were restricted, and then open the whole conversation to see what came before and after.

> Note: Only **AI Studio Admins** can use conversation monitoring. For details, see [AI Studio Roles and Permissions](../ru-men-zhi-nan/ai-studio-jue-se-yu-quan-xian-shuo-ming.md).

## Opening conversation monitoring

Click **Conversation** in the **Analytics** group of the left-side menu.

## Page overview

<figure><img src="../.gitbook/assets/conversation-list.png" alt=""><figcaption></figcaption></figure>

<table data-search="false"><thead><tr><th width="90">Item</th><th width="157">Action</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Column Settings</td><td>Show or hide columns, or pin them</td></tr><tr><td>2</td><td>Refresh</td><td>Reload the list</td></tr><tr><td>3</td><td>Filter</td><td>Filter by message, Agent, creator, source, event or created time. You can add several conditions</td></tr><tr><td>4</td><td>Search</td><td>Search by keyword</td></tr></tbody></table>

By default, the list is sorted by created time, newest first. The columns are:

| Column | Description |
| --- | --- |
| Message | The message the user sent. Click it to open the full conversation it belongs to; see "Viewing the full conversation" below |
| Agent | The Agent that responded to this message |
| Creator | The user who sent this message |
| Source | The screen or channel this message came from; see "Conversation sources" below |
| Event | Abnormal events that occurred during execution, shown as tags whose color depends on the event group. Shows "-" when there is no event; see "Abnormal events" below |
| Created Time | When the message was sent |

## Conversation sources

The **Source** column shows the screen or channel each message came from:

| Source | Description |
| --- | --- |
| Workspace | The user chatted with the Agent in the Workspace |
| Debug Preview | A conversation in the Debug Preview on the Agent settings page, or in the test preview of the workflow editor |
| Schedule | Run triggered by a schedule |
| Dashboard | A question asked in a dashboard |
| Dashboard Conversion | A conversation related to a dashboard |
| Agent API | An external system called the Agent through the Agent API |
| Web App | A conversation through a Web App embedded in a website |
| Webhook | An external system sent an event to the Agent through a Webhook |

> Older conversation data has no recorded source, so the **Source** column shows "-".

## Abnormal events

If something abnormal happens while a conversation runs, the **Event** column shows the corresponding event tag, so you can quickly filter out conversations with problems. When one message has several events, "+number" appears next to the tag; hover over it to see the other events.

When you filter by event, events are divided into the following four groups:

### Failures & Blocks

| Event | Description |
| --- | --- |
| Guardrail Block | The content triggered a guardrail rule and was blocked |
| Provider Content Block | The model provider refused to respond for safety or content policy reasons |
| Tool Call Failed | A tool call failed, for example because of wrong parameters, an unavailable tool or a timeout |
| Skill Load Failed | A skill could not be found or its content could not be read |
| Skill Execution Failed | A skill failed or timed out |
| Skill Build Failed | Building, validating or saving a skill with Skill Builder failed |
| Model Call Failed | The model service was unavailable, the connection timed out or the response was abnormal |
| Knowledge Base Failed | Knowledge base retrieval, embedding or reranking failed (zero search results does not count) |
| Attachment Processing Failed | Reading, converting or parsing an attachment failed |
| Artifact Delivery Failed | A generated file could not be uploaded or made available for download |
| Workflow Failed | A workflow node, variable or branch failed |
| Unclassified Execution Error | Execution definitely failed, but cannot be put in any of the categories above |

### Limits & Incomplete Results

| Event | Description |
| --- | --- |
| Guardrail Mask | The content triggered a guardrail rule and part of it was masked |
| Budget / Quota Exceeded | Not enough budget or quota |
| Model Rate Limited | The model or provider limited the request rate |
| Response Incomplete | The response was not completed, for example because the output Tokens ran out or the model returned no content |
| Tool Call Limit Reached | The number of tool calls reached the limit |

### Execution Adjustments

| Event | Description |
| --- | --- |
| Fallback Model Used | The primary model was unavailable, so a fallback model completed the response. This is informational; the response may still have succeeded |

### Permission Denied

| Event | Description |
| --- | --- |
| Permission Denied | The user does not have permission to use a resource such as a model, tool, skill or file |

## Viewing the full conversation

Each row in the list shows a single message. Click a message to open the whole conversation it belongs to on the right.

<figure><img src="../.gitbook/assets/conversation-session.png" alt=""><figcaption></figcaption></figure>

<table data-search="false"><thead><tr><th width="90">Item</th><th width="157">Action</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Conversation name</td><td>Shows the conversation name and Session ID</td></tr><tr><td>2</td><td>Download Session</td><td>Download the record of the whole conversation</td></tr><tr><td>3</td><td>Close</td><td>Close the drawer and return to the list</td></tr><tr><td>4</td><td>Session</td><td>Shows the whole conversation</td></tr><tr><td>5</td><td>Summary</td><td>Shows the conversation summary generated automatically by AI. Short conversations may not get a summary, in which case "A summary has not been generated for this conversation yet." is shown</td></tr><tr><td>6</td><td>Selected message</td><td>The message you clicked in the list is highlighted with a gray background, and the view starts at the beginning of that message</td></tr></tbody></table>
