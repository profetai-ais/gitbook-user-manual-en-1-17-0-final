---
description: >-
  AI Studio lets IT staff connect externally subscribed large language model
  (LLM) services such as ChatGPT or Gemini, or on-premises LLMs deployed on your
  own compute.
---

# Model

The **Model** page is where you add and manage the models available in AI Studio, including the provider, connection credentials, model type, cost and Token limits, supported capabilities, and model permissions.

Path: **System Setting > Model**

## The model list

The model list has the following columns:

| Column        | Description                                                                 |
| ------------- | --------------------------------------------------------------------------- |
| Enabled       | Whether the model is currently enabled. A green dot means it is.              |
| Name          | The model's name in AI Studio. Click it to open the model's detailed settings. |
| Creator       | The user who created the model.                                               |
| Modified      | When the model was last modified.                                             |
| Tag           | The capability types the model supports.                                      |

**Edit** and **Delete** are available on the right of each row.

### Shared actions

* **Search**: find models by name.
* **Create**: add a model and its connection information.
* **Column settings**: choose which columns to show or hide, and pin a column's position.
* **Refresh**: reload the model list.
* **Filter**: filter by enabled state, name, creator, modified date, provider or tag.
* **Rows per page**: change how many models are shown per page.
* **Pagination**: go to the first, previous, next or last page.

## Creating a model

<figure><img src="../.gitbook/assets/image (381).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (382).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (383).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (384).png" alt=""><figcaption></figcaption></figure>

1. Click **Create**.
2. Enter the model name.
3. Select the provider.
4. Select or enter the base model.
5. Select the tags the model supports.
6. Fill in the model credentials and connection information that provider requires.
7. Expand **Advanced settings** if needed to adjust cost, Token limits, model capabilities and reasoning effort.
8. Click **Test** to confirm the credentials and connection settings work.
9. Once the test passes, click **Create** to save the model, or **Cancel** to discard it.

Fields marked with an asterisk (\*) are required. The **Create** button stays disabled until they are filled in.

{% hint style="warning" %}
API Keys, AWS credentials and service account credentials are all sensitive. Do not put them in screenshots or public documents, or give them to people who do not need them.
{% endhint %}

## Providers

The providers currently available are:

* OpenAI
* Azure
* Google
* Ollama
* Claude
* AWS Bedrock
* Google Vertex AI
* DeepSeek
* Mistral AI
* Cohere
* OpenRouter
* MixRoute
* NVIDIA NIM
* GLM
* MiniMax
* Qwen
* vLLM

Selecting a provider shows the credential and connection fields it needs.

### Common fields

| Field            | Description                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| Base model       | Used to fill in the default cost, Token limits, available capabilities and reasoning effort options; it is not the model actually called. |
| Model            | The model name or identifier actually sent to the provider. It is filled in when you select a base model, and can still be edited. |
| Tag              | The capability types this model can provide.                                                       |
| API Key          | The API Key needed to connect to the model service.                                                |
| API base URL     | The model service's API address.                                                                    |
| Organization     | OpenAI's organization identifier; leave it blank if you do not use one.                             |
| API version      | The API version used by the Azure model service.                                                    |

Some providers need extra information:

* **AWS Bedrock**: you can set the Bedrock API Key, AWS access key ID, AWS secret access key, AWS region and AWS session token.
* **Google Vertex AI**: requires the GCP project ID, the Vertex location and service account credentials.
* **Ollama**: mainly the API base URL; fill in the API Key according to your service environment.

### Provider icons

The icon in the model list reflects the provider selected when the model was created or edited.

<figure><img src="../.gitbook/assets/image (415).png" alt="" width="561"><figcaption></figcaption></figure>

If the icon does not match the source you actually connected to, open the model's detailed settings and check that the provider is correct. The actual call still uses the API base URL, API Key and the other connection parameters.

## Model tags

Model tags indicate the kinds of work a model can do. A model can have several tags.

| Tag                | System tag            | Purpose                                            |
| ------------------ | --------------------- | -------------------------------------------------- |
| Audio speech       | `Audio Speech`        | Generates speech.                                   |
| Audio transcription| `Audio Transcription` | Converts audio to text.                              |
| Chat               | `Chat`                | General conversation and Q&A.                        |
| Completion         | `Completion`          | Generates a text completion from the input.           |
| Embedding          | `Embedding`           | Converts text into vectors.                          |
| Image edit         | `Image Edit`          | Edits an existing image.                             |
| Image generation   | `Image Generation`    | Generates images.                                    |
| Moderation         | `Moderation`          | Performs content safety checks.                       |
| OCR                | `OCR`                 | Recognizes text in images or documents.               |
| Realtime           | `Realtime`            | Supports realtime interaction.                        |
| Rerank             | `Rerank`              | Reranks search or retrieval results.                  |
| Responses          | `Responses`           | Uses a model service with the Responses interface.     |
| Search             | `Search`              | Performs search tasks.                                |
| Vector store       | `Vector Store`        | Supports vector database operations.                  |
| Video generation   | `Video Generation`    | Generates video.                                      |

Choose tags that match what the model actually supports, so it is not used for work it cannot do.

## Advanced settings

### Custom cost and limits

With **Custom cost and limits** enabled, you can override the system's built-in model information.

| Field                        | Description                                       |
| ---------------------------- | ------------------------------------------------- |
| Input cost (per million Tokens)  | The cost per million input Tokens.              |
| Output cost (per million Tokens) | The cost per million output Tokens.             |
| Token limit                  | The maximum number of Tokens allowed per call.      |

When it is off, the system uses the cost and Token limits from the model information.

### Available capabilities

With **Available capabilities** enabled, you can specify whether the model supports particular abilities, for example:

* Image understanding
* PDF upload

If you do not customize them, the system uses the default support state from the model information.

### Reasoning Effort

Reasoning Effort sets the levels of thinking the model can offer. Whether this setting appears, and which levels are available, depend on the **base model** you selected; if the base model does not support reasoning effort, the option does not appear in the advanced settings.

![Model reasoning effort settings](../.gitbook/assets/model-thinking-level.png)

1. Enable **Available capabilities** to customize the model's capability settings.
2. Confirm that **Reasoning parameters** is set to **Supported**.
3. In the **Reasoning Effort** list, enable the options to offer users, and adjust their order and the preselected option as needed.

The Minimal, Low, Medium and High shown on screen are just examples for that base model. Switching to another base model shows the levels that model supports.

{% hint style="info" %}
The **base model** is only used to fill in the default cost, Token limits, available capabilities and reasoning effort options. It does not determine the model actually called — the **Model** field does.
{% endhint %}

{% hint style="info" %}
Cloud models usually come with complete model information, so the system defaults can be used as they are. You normally only need to override them for self-hosted models, special pricing or incomplete model information.
{% endhint %}

## Editing a model

<figure><img src="../.gitbook/assets/image (778).png" alt=""><figcaption></figcaption></figure>

Click a model name to open its detailed settings page. **Edit** and **Delete** are also available on the right of each row.

On the **General** tab you can change:

* The enabled state
* The model name
* The provider
* The base model
* The model tags
* The model credentials
* The advanced settings

When you are done, click **Test** to confirm the connection, then **Save** to apply the changes. Click **Cancel** to discard them.

A disabled model stays in the list but is not offered as an enabled model.

{% hint style="warning" %}
If a model is already used by an Agent, a knowledge base, the configuration settings or another feature, changing its provider, base model or tags may affect that feature. Run a connection test afterwards and confirm the related features still work.
{% endhint %}

## Connection test

<figure><img src="../.gitbook/assets/image (779).png" alt=""><figcaption></figcaption></figure>

When creating or editing a model, click **Test** to confirm that it can be called.

If the test fails, check the following in order:

1. The provider is correct.
2. The base model name or identifier is correct.
3. The API base URL is correct.
4. The API Key or other credentials are valid.
5. Provider-specific fields such as the Azure API version, AWS region or Vertex location are correct.
6. The model service allows connections from this environment.

## Model recommendations by feature

Several places in AI Studio require a model, such as the chat model an Agent uses, a knowledge base's embedding model, the rerank model, and speech transcription. Different models support different capabilities. Before purchasing model APIs or planning an on-premises deployment, use this section to check whether a model fits your use case, so you don't find out after purchase that it can't be used for certain features.

> The tables are listed in order of recommendation. The models you can actually choose depend on your system administrator's settings.

### Chat models

| Model | Deployment | Recommended role | Tool use | Images / PDF | Speech transcription | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| gpt-6.1-sol | Cloud | Primary | ✓ | ✓ | ✗ | Stronger reasoning; handles about 920K tokens |
| claude-sonnet-5 | Cloud | Primary | ✓ | ✓ | ✗ | Handles about 1M tokens |
| gemini-2.5-pro | Cloud | Primary | ✓ | ✓ | ✓ | Can also handle speech transcription |
| gpt-6-luna | Cloud | Cost-saving | ✓ | ✓ | ✗ | Currently the lowest cost; first choice for reranking |
| gpt-5.6-luna | Cloud | Cost-saving | ✓ | ✓ | ✗ | About twice the cost of gpt-6-luna |
| gpt-5.4-mini | Cloud | Rerank | ✓ | ✓ | ✗ | Fast responses |
| gemini-2.5-flash | Cloud | Speech transcription, Rerank | ✓ | ✓ | ✓ | First choice for speech transcription; fast and low cost |
| Qwen3.8-27B | On-prem | Primary | ✓ | ✓ | ✗ | Deployed and validated internally; adjustable thinking length |
| GLM-5 series | On-prem | Primary | ✓ | Depends on version | ✗ | Thinking cannot be turned off from GLM-5.3 onward |
| DeepSeek-V4 | On-prem | Primary | ✓ | Depends on version | ✗ | Adjustable thinking length |

### Embedding and rerank models

| Model | Deployment | Text embedding | Multimodal embedding | Rerank | Notes |
| --- | --- | --- | --- | --- | --- |
| text-embedding-3-large | Cloud | ✓ | ✗ | ✗ | Higher retrieval quality; most used internally |
| text-embedding-3-small | Cloud | ✓ | ✗ | ✗ | Lower cost |
| gemini-embedding-2 | Cloud | ✓ | ✓ | ✗ | Supports both text and multimodal; used internally |
| Qwen3-Embedding-8B | On-prem | ✓ | ✗ | ✗ | Deployed and validated internally |
| bge-m3 | On-prem | ✓ | ✗ | ✗ | Lower hardware requirements |
| Qwen3-Reranker-8B | On-prem | ✗ | ✗ | ✓ | Deployed and validated internally |

#### Notes

1. **Every chat model can handle both general conversation and reranking**; you can also use a dedicated rerank model for reranking.
2. **When an Agent is bound to a knowledge base, its model must support tool use.**
3. **Speech transcription does not currently support on-premises models**, so on-premises deployments need a cloud model for it. The GPT series (including gpt-6 and Luna) does not support audio input.
4. **Changing a knowledge base's embedding model requires rebuilding the vector data**; while it is rebuilt, Agents that use this knowledge base cannot retrieve content from it. Decide on the embedding model before you create a knowledge base.
5. **A multimodal knowledge base requires both** a multimodal embedding model (gemini-embedding-2 is recommended for cloud; there is currently no recommended on-premises model) and a chat model that can read images. For details, see [Image Search](../zhi-shi-ku-zhi-nan/yi-tu-sou-tu.md).

### Terms

When purchasing, compare against the wording in the model vendor's documentation to confirm the model has the capabilities you need.

| Term used here | Meaning | Common wording in vendor docs |
| --- | --- | --- |
| Tool use | The model can call tools such as knowledge base search when needed | Function Calling, Tool Use |
| Images | Can read image content | Vision, Image Input |
| PDF input | Can read PDF files directly | PDF Input, File Input |
| Audio input | Can read audio directly; required for speech transcription | Audio Input |
| Embedding | Turns text or images into vectors for knowledge base search | Embeddings |
| Multimodal | Can handle several kinds of data, such as text and images, together | Multimodal |
| Rerank | Reorders knowledge base search results by relevance to the question | Rerank |


## Deleting a model

Click **Delete** on the right of a model's row to remove it.

<figure><img src="../.gitbook/assets/image (777).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
Before deleting, confirm that the model is not still used by the configuration settings, an Agent, a knowledge base or another feature, so nothing stops working.
{% endhint %}

## Permissions

{% hint style="info" %}
The Model module is only available to AI Studio Admins, so it has no list-level permission settings.
{% endhint %}

### Model permissions

For role permissions, see [Module Permission Roles - Model permissions](../ru-men-zhi-nan/quan-xian-gong-neng-jie-shao.md#mo-xing).

For permission settings, see [Permission Actions - Object role permissions](../ru-men-zhi-nan/quan-xian-cao-zuo-gong-neng-jie-shao.md#jue-se-quan-xian).
