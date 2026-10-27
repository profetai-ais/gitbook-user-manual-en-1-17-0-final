---
description: >-
  A Workflow Agent lets you design, as a process, how the Agent uses the
  components AI Studio provides to complete complex tasks for users.
---

# Workflow Agent

## **Basic settings**

<figure><img src="../.gitbook/assets/image (698).png" alt=""><figcaption></figcaption></figure>

The Workflow Agent home page has several parts:

1. **Agent feature menu**: contains the links below; each one opens the corresponding settings page.
2. **Basic information**: shows the Agent name, when and by whom it was created and last edited, and its enabled state.
3. **Application settings:** settings for the Agent's behavior, depending on the Agent type.
4. **Debug Preview:** lets you test whether the answers are what you expect.

## **Conversation panel**

The conversation panel contains the prompt template, the Conversation Starter and the action menu settings.

### **Prompt Template**

You can bind an existing or favorited application template (prompt template) to an Agent, so that filling in the required fields speeds up Q&A.

<figure><img src="../.gitbook/assets/Snipaste_2026-09-26_00-39-23.png" alt=""><figcaption></figcaption></figure>

### **Conversation Starter**

#### **Quick questions**

You can define preset conversation content so the Agent offers clickable starting points before the conversation begins, which helps users get going faster.

<figure><img src="../.gitbook/assets/Snipaste_2026-09-26_00-40-05.png" alt=""><figcaption></figcaption></figure>

#### **Greeting**

Sets the Agent's initial greeting message. When a user selects this Agent and starts a conversation, the Agent sends this message first to open the conversation.

<figure><img src="../.gitbook/assets/Snipaste_2026-09-26_00-40-28.png" alt=""><figcaption></figcaption></figure>

### **Action menu**

<figure><img src="../.gitbook/assets/image (689).png" alt=""><figcaption></figcaption></figure>

#### **File handling**

When enabled, users can upload files in the conversation input box. Once a file is uploaded, **the Agent decides how to handle it based on the file type and the user's question** — for example reading the file content directly, or calling a suitable tool.

#### **Canvas**

When enabled, the Canvas option appears in the conversation input menu.

Canvas is on by default when an Agent is created.

### **Chat Display**

<figure><img src="../.gitbook/assets/image (690).png" alt=""><figcaption></figcaption></figure>

#### **Human Action**

When enabled, an Action Card appears below a response whenever the Agent needs the user to take part in a decision, confirm an action or provide extra information. Users can complete the interaction, or skip the card and continue the conversation.

#### **Execution process**

When enabled, every Agent response shows the execution process, including the thinking, tool calls, key steps and status, which helps you understand how the Agent completed the task. The execution process updates along with the response, and the thinking message is shown below the content generated so far.

#### **Knowledge base sources**

When enabled, the Agent's responses show the knowledge base sources cited, and the related files are listed under **Reference File**.

When disabled, responses do not show knowledge base citations and **Reference File** does not list knowledge base files. In that case only the Agent Admin and Agent Editor can see which knowledge bases were cited, in the Conversation Log.

## **Debug Preview**

<figure><img src="../.gitbook/assets/image (691).png" alt=""><figcaption></figcaption></figure>

Use this area to test the Agent's responses and adjust the settings accordingly.

Conversations in the Debug Preview apply only to the current test. When you leave the page, the conversation session is reset, and the next time you open the Debug Preview you start a new conversation.

There is currently no other page or conversation history entry point that continues earlier test content. To keep testing, stay on the Debug Preview page.

If you leave the preview and come back, the conversation starts over and cannot be continued. To continue the same conversation, work in the Workspace (the production conversation environment) rather than the Debug Preview.

> Note: Before leaving the Debug Preview page, copy or record any test content you want to keep. If an error message appears during testing, hover over it and click the light-bulb button to ask Copilot. See [Asking Copilot about an error](../ping-tai-zhi-nan/ai-studio-copilot.md#yu-dao-cuo-wu-shi-xun-wen-copilot).

### Uploading files in the **Debug Preview**

* Click the plus sign (+) in the input box to upload a file.

<figure><img src="../.gitbook/assets/image (696).png" alt=""><figcaption></figcaption></figure>

* Drag and drop upload is also supported.

<figure><img src="../.gitbook/assets/image (697).png" alt=""><figcaption></figcaption></figure>

> Note: Files uploaded or produced in the Debug Preview are kept for 30 minutes only.

## Workflow settings

**Workflow settings** in the Agent feature menu is where you edit the Agent's workflow. Clicking it opens the editor for the workflow bound to this Agent.

> For the workflow editor screen and how to use it, see Editing a Workflow.
