# Conversation Log

The Conversation Log stores all of this Agent's conversations. Admins can filter by title, user or date range, and click a column header to sort. The records include the processing steps, so when an error occurs or a response is slow, admins can review the details to diagnose the problem.

* **Conversation summary**: each record has a system-generated summary, for a quick view of the key points.
* **Conversation content**: conversations in the Conversation Log are shown in the same style as in the Workspace. When you open one, the view starts at the beginning of the message you clicked.
* **Window width**: the Conversation Log window opens at the same width as the conversation in the Workspace. Drag the left edge of the window to change its width.

> Note: When a user deletes a conversation in the Workspace, the Conversation Log still keeps its record. Test conversations deleted in the Debug Preview are kept as well, with the source shown as **Debug Preview**.

## Processing steps

<figure><img src="../.gitbook/assets/conversation-log-step-tracking.png" alt=""><figcaption></figcaption></figure>

In a conversation record, click the **View Log** icon below the Agent's response to open the **View Log** window. The **Details** tab shows this response's execution status, execution time, the model used, the source and other information. The **Step Trace** tab lists every node and event that this response went through, in order:

* **Execution status**: each node and tool response is outlined with a color and a status label (for example, failed or timed out), so you can find where an error occurred without expanding every item. Expand an item to see the full error details.
* **Usage and duration**: the right side of each node's title shows the node's Token usage and execution time. Nodes that do not call a model (such as Start and Response) show only the time.
* **Node details**: NODE CONFIG, VARIABLES, INPUT and other details are shown on separate tabs. When you scroll, the node title stays pinned at the top.

Each node, and the whole response, can be downloaded on its own or brought straight into Copilot to ask about it, so you do not have to compile the content yourself:

<table data-search="false"><thead><tr><th width="90">Item</th><th width="157">Action</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Download</td><td>Download this node's record</td></tr><tr><td>2</td><td>Copy</td><td>Copy the content of the current tab</td></tr><tr><td>3</td><td>Ask</td><td>Bring this node's content into Copilot to ask about it, for example to have Copilot explain the cause of an error</td></tr><tr><td>4</td><td>Download</td><td>Download the full record of every node in this response</td></tr><tr><td>5</td><td>Ask</td><td>Bring the full execution record of this response into Copilot to ask about it</td></tr></tbody></table>

For how to use Copilot, see [AI Studio Copilot](../ping-tai-zhi-nan/ai-studio-copilot.md).

## Extracting memories

<figure><img src="../.gitbook/assets/image (717).png" alt=""><figcaption></figcaption></figure>

You can select one or more conversations in the Conversation Log and extract their reusable information as Agent memories.

1. Select the conversations you want to extract memories from.
2. Check the number of selected items shown in the toolbar and click the **Extract memories** button.
3. The system analyzes the selected conversations with an LLM and shows the extraction status: a skip icon means there was nothing suitable to extract, a success icon means the extraction succeeded, and a failure icon means it failed.
4. Successfully extracted content is added to the [Memory](ji-yi.md) page, where you can review and manage it.

## Downloading a conversation

<figure><img src="../.gitbook/assets/image (68).png" alt=""><figcaption></figcaption></figure>

You can download conversation records in JSON format to analyze users' questions, the Agent's execution process and tool usage, or to have another AI tool interpret them.

* **Entire Session**: downloads all conversations in the Session.
* **Single conversation**: downloads the full record of one conversation only, including the conversation content, tool execution records and timing information.
