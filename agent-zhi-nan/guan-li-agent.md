# Managing Agents

## **Agent types**

<figure><img src="../.gitbook/assets/image (659).png" alt=""><figcaption></figcaption></figure>

* **Chat Agent**: interacts directly with an internal or external large language model through basic Q&A.
* **Workflow Agent**: lets you orchestrate a workflow to handle more complex scenarios.

## **Creating an Agent**

<figure><img src="../.gitbook/assets/image (663).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (694).png" alt=""><figcaption></figcaption></figure>

1. Click the **+ Create** button in the upper right of the screen.
2. Select the **Agent type** in the dialog.
3. Enter a name in the **Name** field, then click the button on the right to add multilingual labels. See [Multilingual settings](guan-li-agent.md#duo-guo-yu-yan-she-ding).
4. Enter a description in the **Description** field, then click the button on the right to add multilingual labels. See [Multilingual settings](guan-li-agent.md#duo-guo-yu-yan-she-ding).
5. Click the **Tag** menu and select the tags to apply to this Agent.
6. Click the **Model** menu and select the large language model this Agent uses. You can search by keyword.
7. Click **Save** to finish. The system takes you straight to the Agent edit screen to complete the setup.

> Note: Once an Agent is created, its **Agent type** cannot be changed. The **Model** can be swapped at any time in the inference parameters.

### Multilingual settings <a href="#duo-guo-yu-yan-she-ding" id="duo-guo-yu-yan-she-ding"></a>

<figure><img src="../.gitbook/assets/image (749).png" alt=""><figcaption></figcaption></figure>

1. Click the globe button to translate automatically. You can also edit the content manually.
2. When the automatic translation is done, click **OK** to save.

> Note: The large language models available in the **Model** menu depend on the configuration of your installed environment. The options shown in this manual are for reference only.

## Quick-editing an Agent

<figure><img src="../.gitbook/assets/image (48).png" alt=""><figcaption></figcaption></figure>

In the Agent list, click the edit button on a row to open the quick edit window, where you can change the name and description and switch the Agent's enabled state directly. For other settings (such as inference parameters, knowledge bases and tools), click the Agent's name to open the Agent's settings page.

## Copying an Agent

<figure><img src="../.gitbook/assets/image (47).png" alt=""><figcaption></figcaption></figure>

1. In the Agent list, hover over the Agent you want to copy and click **Copy**.
2. The confirmation window is pre-filled with the original Agent's name. You can change it to a new name so the copy is easy to tell apart from the original.
3. Click confirm to create the copy, or click cancel to close the window without creating it.

## Viewing the Agents that use an Agent

<figure><img src="../.gitbook/assets/agent-in-use-button.png" alt=""><figcaption></figcaption></figure>

An Agent can be added to another Agent's **Coordination** and used as a SubAgent. Before you change or delete an Agent, you can check which Agents use it, so you do not affect their responses.

Hover over any row in the Agent list and click the **Agents in use** button to see which Agents currently use this Agent as a SubAgent.

<figure><img src="../.gitbook/assets/agent-in-use-dialog.png" alt=""><figcaption></figcaption></figure>

The window lists each parent Agent's publish status, name and creator, and the SubAgents it uses. If no Agent uses it, the window shows that there is no data.

### Deleting an Agent that is in use

An Agent that another Agent is using as a SubAgent cannot be deleted directly. The system shows the message "This Agent is currently used as a SubAgent by the following Agents. Remove it from these Agents before deleting it." Go to the **Coordination** of each listed Agent and remove it there, then come back and delete it.

## Exporting and importing an Agent (JSON)

Export and import can be used to back up Agent settings, move settings between environments, or quickly duplicate a similar Agent to save repeated configuration work.

### Exporting an Agent

<figure><img src="../.gitbook/assets/image (660).png" alt=""><figcaption></figcaption></figure>

1. Go to the Agent list, or open the edit page of the Agent you want.
2. Hover over the Agent's row in the table.
3. Click **Export**. The system downloads a proas file.

### Importing an Agent

<figure><img src="../.gitbook/assets/image (661).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (662).png" alt=""><figcaption></figcaption></figure>

1. Click the add button and select **From device**.
2. Click the field and select the file to import.
3. Click **OK** to import the selected file.

## Publishing an Agent

<figure><img src="../.gitbook/assets/image (261).png" alt=""><figcaption></figcaption></figure>

Every Agent type shares the same **Basic Settings** block on its home page, which contains the **Enabled** toggle and a **Settings** button for updating the Agent's name and description. Clicking the settings button opens the following dialog:

1. **Agent publish status**: change the Agent's enabled state. Flipping the toggle takes effect immediately.
2. **Basic settings**: edit the name, description and the multilingual translations.

### Publishing an Agent to the Workspace

An Agent does not automatically appear in Explore in the Workspace after it is created or saved. For other users in the Workspace to find and use it, you have to open the Agent settings, select **Publish** and save.

* **Unpublished:** the Agent appears only under **My Agent**.
* **Published:** the Agent appears under both **My Agent** and **Explore**, with a green publish indicator.

### Setting an Agent's **publish** status

<figure><img src="../.gitbook/assets/image (262).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (263).png" alt=""><figcaption></figcaption></figure>

1. Click the publish status field to open the panel.
2. Click the publish button.
3. In the **Chat in Workspace** field, click the copy button to copy the URL of this Agent's conversation window in the Workspace, so you can share it with users to open the conversation directly.
4. Click the chat button to open the conversation in the Workspace.
5. Click the unpublish button to unpublish the Agent.

When users open the **Chat in Workspace** URL, they go to the Workspace with the left-side navigation menu still visible. For details, see [Workspace Overview](../gong-zuo-kong-jian-zhi-nan/ai-studio-gong-zuo-kong-jian.md).

### If you cannot find an Agent

If an Agent does not appear in the public space, check the following in order:

* Go to **My Agent** and confirm the Agent is still listed there.
* Open the Agent's settings page and confirm that **Publish** is selected.
* After saving, go back to **Workspace > Explore** and look again.
* If it still does not appear, refresh the page and confirm the Agent was published to the correct Workspace.

> Creating an Agent and publishing an Agent are two separate steps. An Agent only appears in Explore in the Workspace once it has been published.

## Copying the URL of an Agent's settings page

When you open an Agent from the Agent list, there is a share button next to the publish status at the top of the screen. Click it to copy the URL of this Agent's settings page, which you can share with other Agent admins so they can open the settings page directly.

> Note: The share button copies the URL of the **Agent settings page**. To let users start a conversation directly, use the copy button in the **Chat in Workspace** field of the publish menu instead.

## Permissions

For list permissions, see [Module Permission Roles - Agent list permissions](../ru-men-zhi-nan/quan-xian-gong-neng-jie-shao.md#agent-qing-dan).

For permission settings, see [Permission Actions - Root permissions](../ru-men-zhi-nan/quan-xian-cao-zuo-gong-neng-jie-shao.md#root-quan-xian).
