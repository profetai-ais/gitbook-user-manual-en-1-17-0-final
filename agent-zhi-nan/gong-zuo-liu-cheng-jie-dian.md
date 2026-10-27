# Workflow Nodes

## Introduction

The workflow system offers a variety of nodes for building flexible, intelligent and modular Agents. Each node plays a different role in the system's logic, user interaction and backend integration.

<figure><img src="../.gitbook/assets/image (764).png" alt=""><figcaption></figcaption></figure>

<table data-search="false"><thead><tr><th width="80">Item</th><th width="160">Node</th><th>What it does in a workflow</th></tr></thead><tbody><tr><td>1</td><td>Knowledge</td><td>Retrieves relevant information from an internal knowledge base or document database.</td></tr><tr><td>2</td><td>LLM</td><td>Runs a prompt with a language model (for example GPT-5.2 Thinking, GPT-5.2 Instant or Gemini 3) to generate or reason over the current input.</td></tr><tr><td>3</td><td>Response</td><td>Defines what the user actually sees — outputs and displays the Agent's reply.</td></tr><tr><td>4</td><td>Note</td><td>Adds an internal note or annotation to the canvas; not connected to the actual logic.</td></tr><tr><td>5</td><td>Variable</td><td>Captures, stores or transforms a value from an earlier step for later nodes to use.</td></tr><tr><td>6</td><td>Human Input</td><td>Waits for the user to choose, then continues along the branch matching their choice.</td></tr><tr><td>7</td><td>Guardrails</td><td>Checks and restricts content within the process, which helps reduce the risk of personal data leaks, security issues and compliance problems, and keeps the output within your rules.</td></tr><tr><td>8</td><td>Classification</td><td>Labels the input or routes it automatically, based on predefined logic or model-based classification.</td></tr><tr><td>9</td><td>Fork</td><td>Describes how and in what order data flows between nodes, so tasks can run automatically.</td></tr><tr><td>10</td><td>Merge</td><td>Brings the outputs of different branches back into one node and hands them on together.</td></tr></tbody></table>

## **Knowledge**

Retrieves relevant information from an internal knowledge base or document database.

<div align="center" data-with-frame="true"><figure><img src="../.gitbook/assets/image (140).png" alt="" width="375"><figcaption></figcaption></figure></div>

<table><thead><tr><th width="80">Item</th><th width="160">Field</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Knowledge retrieval</td><td>The input content (type "/" and select query for the user's question)</td></tr><tr><td>2</td><td>Knowledge base reference</td><td>Select the knowledge bases you need</td></tr><tr><td>3</td><td>Retrieval parameters</td><td>See "Testing a knowledge base - retrieval parameter settings"</td></tr></tbody></table>

## **LLM**

Runs a prompt with a language model (for example GPT-5.2 Thinking, GPT-5.2 Instant or Gemini 3) to generate or reason over the current input.

<div data-with-frame="true"><figure><img src="../.gitbook/assets/image (141).png" alt="" width="188"><figcaption></figcaption></figure></div>

<table data-search="false"><thead><tr><th width="80">Item</th><th width="160">Field</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>LLM name</td><td>Enter a node name to make it easier to identify</td></tr><tr><td>2</td><td>LLM parameters</td><td>See Parameters</td></tr><tr><td>3</td><td>Model</td><td>Change the language model this node uses (the same model setting as in 2)</td></tr><tr><td>4</td><td>Context</td><td>The input content (type "/" and select query for the user's question)</td></tr><tr><td>5</td><td>Use node files</td><td>Which files the LLM may take from earlier nodes</td></tr><tr><td>6</td><td>File handling</td><td>See File handling</td></tr><tr><td>7</td><td>Enable Knowledge Base</td><td>See Knowledge base sources</td></tr><tr><td>8</td><td>Coordination</td><td>See Coordination</td></tr><tr><td>9</td><td>Skill</td><td>See Skill</td></tr><tr><td>10</td><td>Reference Memory</td><td>When enabled, the LLM refers to the memories in the memory store when responding. For how memories are saved, see Agent Memory</td></tr><tr><td>11</td><td>Conversation memory</td><td>See conversation memory under Parameters</td></tr><tr><td>12</td><td>Tool</td><td>See Tools</td></tr></tbody></table>

## **Response**

The Response node defines the **Agent's final output**. It returns the results compiled in the workflow to the user, or as the response for downstream systems.

<div data-with-frame="true"><figure><img src="../.gitbook/assets/image (142).png" alt="" width="246"><figcaption></figcaption></figure></div>

<table><thead><tr><th width="80">Item</th><th width="160">Field</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Node name</td><td>Enter a node name to make it easier to identify</td></tr><tr><td>2</td><td>Description</td><td>Describe what this node is for</td></tr><tr><td>3</td><td>Configure variables</td><td>Type "/" to configure variables</td></tr></tbody></table>

## **Note**

Adds an internal note or annotation to the canvas; not connected to the actual logic.

<div data-with-frame="true"><figure><img src="../.gitbook/assets/image (143).png" alt="" width="249"><figcaption></figcaption></figure></div>

<table><thead><tr><th width="80">Item</th><th width="160">Field</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Node name</td><td>Enter a node name to make it easier to identify</td></tr><tr><td>2</td><td>Note</td><td>Enter note content for later reference</td></tr></tbody></table>

## **Variable**

Captures, stores or transforms a value from an earlier step for later nodes to use.

<div data-with-frame="true"><figure><img src="../.gitbook/assets/image (144).png" alt="" width="375"><figcaption></figcaption></figure></div>

<table><thead><tr><th width="80">Item</th><th width="200">Field</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Variable (global variable name)</td><td>Selects or specifies the <strong>global variable key</strong> to write to (for example <code>global.age</code>), so later nodes can read and reference it by a consistent name.</td></tr><tr><td>2</td><td>Variable content (value)</td><td>Sets the global variable's <strong>actual value</strong>, for later nodes to use directly.</td></tr></tbody></table>

## Guardrails

Checks and restricts content within the process, blocking or masking it according to your settings, to reduce the risk of personal data leaks, security issues and content compliance problems.

<div data-with-frame="true"><figure><img src="../.gitbook/assets/image (145).png" alt="" width="375"><figcaption></figcaption></figure></div>

<table><thead><tr><th width="80">Item</th><th width="160">Field</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Configure variables</td><td>Type "/" to configure variables</td></tr><tr><td>2</td><td>Block / Mask</td><td>Select how the guardrail works</td></tr><tr><td>3</td><td>Category</td><td>Select the content to block or mask by category</td></tr></tbody></table>

## **Classification**

Labels the input or routes it automatically, based on predefined logic or model-based classification.

<div data-with-frame="true"><figure><img src="../.gitbook/assets/image (146).png" alt="" width="375"><figcaption></figcaption></figure></div>

<table><thead><tr><th width="80">Item</th><th width="160">Field</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Model</td><td>Change the language model this node uses</td></tr><tr><td>2</td><td>Context</td><td>The input content (type "/" and select query for the user's question)</td></tr><tr><td>3</td><td>Category</td><td>Classify the question. The node no longer provides a default category; add the categories you need</td></tr></tbody></table>

> When you open an existing workflow that contains a Classification node, the original "Default" category is automatically renamed "Other". After you save, the workflow is stored in the new format, and the branches that were already connected are not affected.

## Fork

Describes how and in what order data flows between nodes, so tasks can run automatically.

<div data-with-frame="true"><figure><img src="../.gitbook/assets/image (147).png" alt="" width="375"><figcaption></figcaption></figure></div>

<table><thead><tr><th width="80">Item</th><th width="160">Field</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Branches</td><td>View the current number of branches</td></tr><tr><td>2</td><td>Branch status</td><td>View the current branch status</td></tr></tbody></table>

## Merge

Brings the outputs of different branches back into one node and hands them on together.

<div data-with-frame="true"><figure><img src="../.gitbook/assets/image (148).png" alt="" width="375"><figcaption></figcaption></figure></div>

<table><thead><tr><th width="80">Item</th><th width="160">Field</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Waiting</td><td>View the number of nodes being waited for</td></tr><tr><td>2</td><td>Input status</td><td>View the current input status</td></tr><tr><td>3</td><td>Wait timeout</td><td>Set the wait timeout</td></tr></tbody></table>

## **Human Input**

Pauses the process and shows a message with action buttons. Once the user chooses, the process continues along the branch matching their choice. You can also have someone else confirm, which suits processes that need a manager's or owner's approval before they continue.

<div data-with-frame="true"><figure><img src="../.gitbook/assets/Frame 343.png" alt="" width="300"><figcaption></figcaption></figure></div>

<table><thead><tr><th width="80">Item</th><th width="160">Field</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Message</td><td>The message shown to the person responding; type "/" to configure variables. Put any extra explanation of the actions here as well</td></tr><tr><td>2</td><td>User Actions</td><td>The actions to choose from. Each action takes a single value (up to 100 characters), which is shown on the button and is also the value used for branching. At least one action is required</td></tr><tr><td>3</td><td>Confirmed by</td><td>Choose who responds; the process waits for the confirmer's response before it continues:<br>• <strong>Current User</strong>: the user currently interacting with the Agent in this conversation responds<br>• <strong>Specified User</strong>: the selected user responds, regardless of who is interacting with the Agent. Select one confirmer, who can be yourself or someone else</td></tr><tr><td>4</td><td>Notification</td><td>System notifications are on by default and cannot be turned off; the confirmer is notified when the process starts waiting for a response. You can also select E-mail Notification to notify the confirmer by email as well</td></tr><tr><td>5</td><td>Timeout</td><td>The wait duration and unit (seconds, minutes, hours, days). If no response arrives in time, the process continues through the timeout exit</td></tr></tbody></table>

{% hint style="info" %}
Action text is shown directly on the buttons, so keep it short and clear, no more than one or two lines. Buttons have no hover description; if the actions need explaining, put it in the Message.
{% endhint %}

Each user action creates a matching exit on the node, plus a fixed **timeout** exit. Every exit has to be connected to a downstream node before the workflow can be saved.

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

In a downstream node, type "/" and select "node name.{selected}" to get the value of the action the user chose. When the process continues through the timeout exit, this value is empty.

### Who responds

The Confirmed by setting decides who responds to the Human Input node. Whichever option you choose, the confirmer is reminded by a system notification when the process starts waiting for a response.

<table><thead><tr><th width="240">Setting</th><th>How to respond</th></tr></thead><tbody><tr><td>Current User</td><td>The user talking to the Agent responds, either on the card in the conversation or from the notification</td></tr><tr><td>Specified User, and the confirmer is the user in the conversation</td><td>Respond on the card in the conversation, or from the notification</td></tr><tr><td>Specified User, and the confirmer is not the user in the conversation</td><td>The card shows "Waiting for ○○ to respond". The user in the conversation cannot respond and has to wait for the confirmer to respond from the notification</td></tr></tbody></table>

With Specified User, the same confirmer responds no matter who is talking to the Agent. For example, if you set a manager as the confirmer, the process continues only after the manager confirms, whoever reaches this node.

The confirmer does not need permission for the Agent to respond: a confirmer without permission can still click an action in the system notification or email, but cannot return to the conversation.

### The card in the conversation

When the process reaches a Human Input node, a card appears in the conversation with the message, the action buttons and the expiry time. Once a response is given, the process continues through the chosen action's exit.

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption><p>Human Input node triggered</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption><p>Human Input node timed out</p></figcaption></figure>

* While the process is waiting for a response, no new messages can be sent in that conversation until the response is given.
* Card states are "Waiting", "Answered", "Timed out" and "Cancelled". When a confirmer is specified, a waiting card shows "Waiting for (confirmer name)". After an answer, while the process has not yet continued, the card shows "Waiting". Status labels are shown in full and are not truncated.
* If you reopen the conversation, a waiting card is still there and can still be answered.
* If the response is stopped while waiting, the card is shown as canceled and the process does not continue.
* The confirmer can respond by clicking an action in the system notification, or click "Back to conversation" to respond in the original conversation. After a response the action buttons in the notification are collapsed; after a timeout or cancellation they can no longer be clicked. For how the notification looks, see [System Notification](../ping-tai-zhi-nan/xi-tong-tong-zhi.md).
* With E-mail Notification selected, the confirmer can also respond directly in the email; see "Email notification" below.
* Calling a Workflow Agent that contains a Human Input node through Coordination is not supported yet.

### Email notification

With E-mail Notification selected, the confirmer receives an email from Profet AI AIS (ais@profetai.com) when the process starts waiting for a response, and can respond by choosing an action in the email without opening AIS.

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption><p>Email notification from a Human Input node</p></figcaption></figure>

The email contains:

<table><thead><tr><th width="160">Item</th><th>Description</th></tr></thead><tbody><tr><td>Subject</td><td>Shows the source Agent and "Your response is needed", followed by the item to confirm</td></tr><tr><td>Body</td><td>Shows the Agent name, the item to confirm and the message set in the node</td></tr><tr><td>Response deadline</td><td>The deadline after "Expires at", currently shown in UTC. After the deadline, the process continues through the timeout exit</td></tr><tr><td>Action buttons</td><td>The same as the user actions set in the node; click one to send your response</td></tr></tbody></table>

To respond:

1. Open the email and check what needs confirming and the response deadline.
2. Click one of the action buttons in the email. You need to sign in to AIS before the response is sent.
3. A result page opens in your browser. "Submitted" means the response was sent, and the process continues according to the chosen action.
4. Click "Back To Homepage" to return to the AIS homepage.

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption><p>Response submitted</p></figcaption></figure>

If the result page shows an error message, such as "The selected human input action does not exist.", the response was not sent. Go back to the conversation in AIS and check the card's current status, for example whether it has timed out, been canceled or already been answered another way.

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption><p>Response failed</p></figcaption></figure>
