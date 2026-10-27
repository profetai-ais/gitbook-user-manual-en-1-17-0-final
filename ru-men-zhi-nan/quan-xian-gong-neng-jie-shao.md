---
description: This page explains the permission roles of each module.
---

# Module Permission Roles

## **Agent module permissions**

### **Agent list** <a href="#agent-qing-dan" id="agent-qing-dan"></a>

The table below describes what can be done at the "Agent list" level. Think of the Agent list as a management scope: whether you can create items, manage members, and view or edit every item depends on the role you have been granted for this feature list.

<figure><img src="../.gitbook/assets/image (594).png" alt=""><figcaption></figcaption></figure>

<table data-full-width="true"><thead><tr><th>Role</th><th>Agent List Admin</th><th>Agent List User</th></tr></thead><tbody><tr><td><strong>Description</strong></td><td>Can use every feature of the Agent list and of Agents</td><td>Can create and edit their own Agents</td></tr><tr><td><strong>Create an Agent</strong></td><td>O</td><td>O</td></tr><tr><td><strong>Manage Agent list members</strong></td><td>O</td><td>X</td></tr><tr><td><strong>View all Agents</strong></td><td>O</td><td>X</td></tr><tr><td><strong>Edit all Agents</strong></td><td>O</td><td>X</td></tr></tbody></table>

### Agent <a href="#agent" id="agent"></a>

The table below describes what can be done at the "Agent" level. At this level the **Agent Admin** or **Agent Editor** usually manages members and assigns the appropriate permissions to editors and users.

<figure><img src="../.gitbook/assets/image (595).png" alt=""><figcaption></figcaption></figure>

<table data-full-width="true"><thead><tr><th>Role</th><th>Agent Admin</th><th>Agent Editor</th><th>Agent User</th></tr></thead><tbody><tr><td><strong>Description</strong></td><td>Has full control of the Agent</td><td>Can help manage how the Agent is used and adjust its content</td><td>Can only use the Agent in the Workspace</td></tr><tr><td><strong>Use the Agent in the Workspace</strong></td><td>O</td><td>O</td><td>O</td></tr><tr><td><strong>View the Agent in the Agent list</strong></td><td>O</td><td>O</td><td>X</td></tr><tr><td><strong>Manage Agent members</strong></td><td>O</td><td>O</td><td>X</td></tr><tr><td><strong>Edit the Agent</strong></td><td>O</td><td>O</td><td>X</td></tr><tr><td><strong>Delete the Agent</strong></td><td>O</td><td>X</td><td>X</td></tr></tbody></table>

> Note: An Agent Admin or Agent Editor can remove a knowledge base, tool, skill, SubAgent or prompt template from the Agent settings even if they do not have permission to use that item.

## **Knowledge Base module permissions**

### Knowledge Base list <a href="#zhi-shi-ku-qing-dan" id="zhi-shi-ku-qing-dan"></a>

The table below describes what can be done at the "Knowledge Base list" level. Think of the Knowledge Base list as a management scope: whether you can create items, manage members, and view or edit every item depends on the role you have been granted for this feature list.

<figure><img src="../.gitbook/assets/image (596).png" alt=""><figcaption></figcaption></figure>

<table data-full-width="true"><thead><tr><th>Role</th><th>Knowledge Base List Admin</th><th>Knowledge Base List User</th></tr></thead><tbody><tr><td><strong>Description</strong></td><td>Can use every feature of the knowledge base and of knowledge</td><td>Can create and edit their own knowledge</td></tr><tr><td><strong>Create knowledge</strong></td><td>O</td><td>O</td></tr><tr><td><strong>Manage Knowledge Base members</strong></td><td>O</td><td>X</td></tr><tr><td><strong>View all knowledge</strong></td><td>O</td><td>X</td></tr><tr><td><strong>Edit all knowledge</strong></td><td>O</td><td>X</td></tr></tbody></table>

### Knowledge <a href="#zhi-shi" id="zhi-shi"></a>

The table below describes what can be done at the "Knowledge" level. At this level the **Knowledge Admin** or **Knowledge Editor** usually manages members and assigns the appropriate permissions to editors and users.

<figure><img src="../.gitbook/assets/image (597).png" alt=""><figcaption></figcaption></figure>

<table data-full-width="true"><thead><tr><th>Role</th><th>Knowledge Admin</th><th>Knowledge Editor</th><th>Knowledge User</th></tr></thead><tbody><tr><td><strong>Description</strong></td><td>Has full control of the knowledge</td><td>Can help adjust the content of the knowledge</td><td>Can only read the knowledge</td></tr><tr><td><strong>Add the knowledge to an Agent</strong></td><td>O</td><td>O</td><td>O</td></tr><tr><td><strong>View the knowledge in the Knowledge Base list</strong></td><td>O</td><td>O</td><td>X</td></tr><tr><td><strong>Manage knowledge members</strong></td><td>O</td><td>O</td><td>X</td></tr><tr><td><strong>Edit the knowledge</strong></td><td>O</td><td>O</td><td>X</td></tr><tr><td><strong>Delete the knowledge</strong></td><td>O</td><td>X</td><td>X</td></tr></tbody></table>

### **Dataset** <a href="#shu-ju-ji" id="shu-ju-ji"></a>

By assigning users, groups or organizations to a dataset, an administrator controls which users can use that dataset in other features, such as Agent settings, testing or other knowledge-based features.

Once the permission settings are saved, the selected users, groups or organizations can access and use that dataset in the supported features.

<figure><img src="../.gitbook/assets/image (598).png" alt=""><figcaption></figcaption></figure>

## **Skill module permissions**

### **Skill list**

The table below describes what can be done at the "Skill list" level. Think of the Skill list as a management scope: whether you can create items, manage members, and view or edit every item depends on the role you have been granted for this feature list.

<figure><img src="../.gitbook/assets/image (599).png" alt=""><figcaption></figcaption></figure>

<table data-full-width="true"><thead><tr><th>Role</th><th>Skill List Admin</th><th>Skill List User</th></tr></thead><tbody><tr><td><strong>Description</strong></td><td>Can use every feature of the Skill list and of skills</td><td>Can create and edit their own skills</td></tr><tr><td><strong>Create a skill</strong></td><td>O</td><td>O</td></tr><tr><td><strong>Manage skill members</strong></td><td>O</td><td>X</td></tr><tr><td><strong>View all skills</strong></td><td>O</td><td>X</td></tr><tr><td><strong>Edit all skills</strong></td><td>O</td><td>X</td></tr></tbody></table>

### **Skill**

The table below describes what can be done at the "Skill" level. At this level the **Skill Admin** or **Skill Editor** usually manages members and assigns the appropriate permissions to editors and users.

<figure><img src="../.gitbook/assets/image (600).png" alt=""><figcaption></figcaption></figure>

<table data-full-width="true"><thead><tr><th>Role</th><th>Skill Admin</th><th>Skill Editor</th><th>Skill User</th></tr></thead><tbody><tr><td><strong>Description</strong></td><td>Has full control of the skill</td><td>Can help adjust the content of the skill</td><td>Can only read the skill</td></tr><tr><td><strong>Add the skill to an Agent</strong></td><td>O</td><td>O</td><td>O</td></tr><tr><td><strong>View the skill in the Skill list</strong></td><td>O</td><td>O</td><td>X</td></tr><tr><td><strong>Set skill members</strong></td><td>O</td><td>O</td><td>X</td></tr><tr><td><strong>Edit the skill</strong></td><td>O</td><td>O</td><td>X</td></tr><tr><td><strong>Delete the skill</strong></td><td>O</td><td>X</td><td>X</td></tr></tbody></table>

## **MCP module permissions**

### **MCP list** <a href="#mcp-qing-dan" id="mcp-qing-dan"></a>

The table below describes what can be done at the "**MCP** list" level. Think of the **MCP** list as a management scope: whether you can create items, manage members, and view or edit every item depends on the role you have been granted for this feature list.

<figure><img src="../.gitbook/assets/image (601).png" alt=""><figcaption></figcaption></figure>

<table data-full-width="true"><thead><tr><th>Role</th><th>MCP List Admin</th><th>MCP List User</th></tr></thead><tbody><tr><td><strong>Description</strong></td><td>Can use every feature of the MCP list and of MCP</td><td>Can create and edit their own MCP</td></tr><tr><td><strong>Create an MCP</strong></td><td>O</td><td>O</td></tr><tr><td><strong>Manage MCP members</strong></td><td>O</td><td>X</td></tr><tr><td><strong>View all MCP</strong></td><td>O</td><td>X</td></tr><tr><td><strong>Edit all MCP</strong></td><td>O</td><td>X</td></tr></tbody></table>

### **MCP** <a href="#mcp" id="mcp"></a>

The table below describes what can be done at the "MCP" level. At this level the **MCP Admin** or **MCP Editor** usually manages members and assigns the appropriate permissions to editors and users.

<figure><img src="../.gitbook/assets/image (602).png" alt=""><figcaption></figcaption></figure>

<table data-full-width="true"><thead><tr><th>Role</th><th>MCP Admin</th><th>MCP Editor</th><th>MCP User</th></tr></thead><tbody><tr><td><strong>Description</strong></td><td>Has full control of the MCP</td><td>Can help adjust the content of the MCP</td><td>Can only read the MCP</td></tr><tr><td><strong>Add the MCP to an Agent</strong></td><td>O</td><td>O</td><td>O</td></tr><tr><td><strong>View the MCP in the MCP list</strong></td><td>O</td><td>O</td><td>X</td></tr><tr><td><strong>Set MCP members</strong></td><td>O</td><td>O</td><td>X</td></tr><tr><td><strong>Edit the MCP</strong></td><td>O</td><td>O</td><td>X</td></tr><tr><td><strong>Delete the MCP</strong></td><td>O</td><td>X</td><td>X</td></tr></tbody></table>

### MCP Tool <a href="#mcp-gong-ju" id="mcp-gong-ju"></a>

By assigning users, groups or organizations to a tool, an administrator controls which users can use that tool in other features, such as Agent settings, testing or other tool-based features.

Once the permission settings are saved, the selected users, groups or organizations can access and use that tool in the supported features.

<figure><img src="../.gitbook/assets/image (603).png" alt=""><figcaption></figcaption></figure>

## **Workflow Template module permissions**

### **Workflow Template list** <a href="#gong-zuo-liu-cheng-mu-ban-qing-dan" id="gong-zuo-liu-cheng-mu-ban-qing-dan"></a>

The table below describes what can be done at the "Workflow Template list" level. Think of the Workflow Template list as a management scope: whether you can create items, manage members, and view or edit every item depends on the role you have been granted for this feature list.

<figure><img src="../.gitbook/assets/image (604).png" alt=""><figcaption></figcaption></figure>

<table data-full-width="true"><thead><tr><th>Role</th><th>Workflow Template List Admin</th><th>Workflow Template List User</th></tr></thead><tbody><tr><td><strong>Description</strong></td><td>Can use every feature of the Workflow Template list and of workflow templates</td><td>Can create and edit their own workflow templates</td></tr><tr><td><strong>Create a workflow template</strong></td><td>O</td><td>O</td></tr><tr><td><strong>Manage Workflow Template list members</strong></td><td>O</td><td>X</td></tr><tr><td><strong>View all workflow templates</strong></td><td>O</td><td>X</td></tr><tr><td><strong>Edit all workflow templates</strong></td><td>O</td><td>X</td></tr></tbody></table>

### Workflow Template <a href="#gong-zuo-liu-cheng-mu-ban" id="gong-zuo-liu-cheng-mu-ban"></a>

The table below describes what can be done at the "Workflow Template" level. At this level the **Workflow Template Admin** or **Workflow Template Editor** usually manages members and assigns the appropriate permissions to editors and users.

<figure><img src="../.gitbook/assets/image (605).png" alt=""><figcaption></figcaption></figure>

<table data-full-width="true"><thead><tr><th>Role</th><th>Workflow Template Admin</th><th>Workflow Template Editor</th><th>Workflow Template User</th></tr></thead><tbody><tr><td><strong>Description</strong></td><td>Has full control of the workflow template</td><td>Can help adjust the content of the workflow template</td><td>Can only read the workflow template</td></tr><tr><td><strong>Use the workflow template in the Workspace</strong></td><td>O</td><td>O</td><td>O</td></tr><tr><td><strong>View the workflow template in the Workflow Template list</strong></td><td>O</td><td>O</td><td>X</td></tr><tr><td><strong>Set workflow template members</strong></td><td>O</td><td>O</td><td>X</td></tr><tr><td><strong>Edit the workflow template</strong></td><td>O</td><td>O</td><td>X</td></tr><tr><td><strong>Delete the workflow template</strong></td><td>O</td><td>X</td><td>X</td></tr></tbody></table>

## **Prompt Template module permissions**

### **Prompt Template list** <a href="#ti-shi-ci-mu-ban-qing-dan" id="ti-shi-ci-mu-ban-qing-dan"></a>

The table below describes what can be done at the "Prompt Template list" level. Think of the Prompt Template list as a management scope: whether you can create items, manage members, and view or edit every item depends on the role you have been granted for this feature list.

<figure><img src="../.gitbook/assets/image (606).png" alt=""><figcaption></figcaption></figure>

<table data-full-width="true"><thead><tr><th>Role</th><th>Prompt Template List Admin</th><th>Prompt Template List User</th></tr></thead><tbody><tr><td><strong>Description</strong></td><td>Can use every feature of the Prompt Template list and of prompt templates</td><td>Can create and edit their own prompt templates</td></tr><tr><td><strong>Create a prompt template</strong></td><td>O</td><td>O</td></tr><tr><td><strong>Manage Prompt Template list members</strong></td><td>O</td><td>X</td></tr><tr><td><strong>View all prompt templates</strong></td><td>O</td><td>X</td></tr><tr><td><strong>Edit all prompt templates</strong></td><td>O</td><td>X</td></tr></tbody></table>

### Prompt Template <a href="#ti-shi-ci-mu-ban" id="ti-shi-ci-mu-ban"></a>

The table below describes what can be done at the "Prompt Template" level. At this level the **Prompt Template Admin** or **Prompt Template Editor** usually manages members and assigns the appropriate permissions to editors and users.

<figure><img src="../.gitbook/assets/image (607).png" alt=""><figcaption></figcaption></figure>

<table data-full-width="true"><thead><tr><th>Role</th><th>Prompt Template Admin</th><th>Prompt Template Editor</th><th>Prompt Template User</th></tr></thead><tbody><tr><td><strong>Description</strong></td><td>Has full control of the prompt template</td><td>Can help adjust the content of the prompt template</td><td>Can only read the prompt template</td></tr><tr><td><strong>Use the prompt template in the Workspace</strong></td><td>O</td><td>O</td><td>O</td></tr><tr><td><strong>View the prompt template in the Prompt Template list</strong></td><td>O</td><td>O</td><td>X</td></tr><tr><td><strong>Set prompt template members</strong></td><td>O</td><td>O</td><td>X</td></tr><tr><td><strong>Edit the prompt template</strong></td><td>O</td><td>O</td><td>X</td></tr><tr><td><strong>Delete the prompt template</strong></td><td>O</td><td>X</td><td>X</td></tr></tbody></table>

## **Model module permissions**

{% hint style="info" %}
The Model module is only available to AI Studio Admins, so it has no list-level permission settings.
{% endhint %}

### **Model** <a href="#mo-xing" id="mo-xing"></a>

The table below describes what can be done at the "Model" level. At this level the **Model Assigner** usually manages members and assigns the appropriate permissions to users.

<figure><img src="../.gitbook/assets/image (608).png" alt=""><figcaption></figcaption></figure>

<table data-full-width="true"><thead><tr><th>Role</th><th>Model Assigner</th><th>Model User</th></tr></thead><tbody><tr><td><strong>Description</strong></td><td>Can manage model settings and the model list, and use the models they have access to</td><td>Can use the models they have access to, but cannot manage models</td></tr><tr><td><strong>Chat in the Workspace with an Agent that uses the model</strong></td><td>O</td><td>O</td></tr><tr><td><strong>Select a model in the model list</strong></td><td>O</td><td>X</td></tr></tbody></table>
