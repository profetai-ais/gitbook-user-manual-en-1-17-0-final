---
description: >-
  This guide walks through configuring an LLM node using the UI elements in the
  workflow editor.
---

# Workflow Node Settings

## Page overview

<figure><img src="../.gitbook/assets/image (149).png" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="80">Step</th><th width="180">Area</th><th>What to do</th></tr></thead><tbody><tr><td>1</td><td>Node name</td><td>Give the LLM node a clear, descriptive name (for example: 2. Industry trends). This keeps the process organized visually and logically, which matters most in complex workflows. <strong>Note:</strong> the node name has to be unique before the settings can be saved.</td></tr><tr><td>2</td><td>Node description</td><td>Give the LLM node a short description (for example: covers industry developments, policy changes, technology drivers and company behavior). This keeps the process organized visually and logically, which matters most in complex workflows.</td></tr><tr><td>3</td><td>Model selection</td><td>Select a language model from the drop-down menu (for example gpt-5.2-thinking or gpt-5.2-instant). Make sure the model fits your response quality and budget needs.</td></tr><tr><td>4</td><td>Context (input variables)</td><td>Sets the input the LLM should refer to when reasoning. You can pass dynamic input using variables from other nodes or from user input. Type <code>/</code> in the context window to see the available variables. ⚠️ To use variables such as <code>result</code>, <code>usage</code> or <code>executionTime</code> from an earlier node, that node has to be <strong>explicitly connected</strong> to the current node, otherwise the context cannot resolve the variable.</td></tr><tr><td>5</td><td>Use node files</td><td>Which files the LLM may take from earlier nodes</td></tr><tr><td>6</td><td>File handling (optional)</td><td>Choose how uploaded files are handled. For more information, see the File handling section.</td></tr><tr><td>7</td><td>Knowledge Base</td><td>When enabled, the selected knowledge is queried automatically during a conversation. The retrieval parameters are the same as in the Agent settings; click the gear icon in the Knowledge Base block to adjust them. For the parameters, see Knowledge Base Parameters.</td></tr><tr><td>13</td><td>Inference settings</td><td>Click the gear icon next to the model selection area to customize the model's behavior, including:<br><em>1. Parameters</em>: Temperature, Top P, Max Tokens (see the parameter table for more information).<br><em>2. System prompt</em>: write a prompt defining the persona, task, tone and tool behavior.</td></tr></tbody></table>

<figure><img src="../.gitbook/assets/image (150).png" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="80">Step</th><th width="180">Area</th><th>What to do</th></tr></thead><tbody><tr><td>8</td><td>Coordination</td><td>Lets the Agent connect to and work with other Agents on a task.</td></tr><tr><td>9</td><td>Skill</td><td>By configuring skills, the Agent can support more features and task scenarios.</td></tr><tr><td>10</td><td>Reference Memory</td><td>When enabled, the personal memory store is referred to during a conversation.</td></tr><tr><td>11</td><td>Memory settings (optional)</td><td>Enable memory if you need multi-turn conversations. Set the memory window size when building multi-turn conversations or reasoning chains (recommended: 3–5). <strong>Note:</strong> we recommend using the same number of session memory turns throughout for consistency and to avoid losing information. ⚠️ One turn is a pair of one question (the user's prompt) and one response (the Agent's answer).</td></tr><tr><td>12</td><td>Tool (optional)</td><td>If a task needs capabilities beyond the LLM itself, attach a tool (for example the <strong>Serper Search</strong> tool for live web search during generation).</td></tr></tbody></table>

## **How to use Context and System Prompt**

When configuring an LLM node, both **Context** and **System Prompt** can contain instructions, but they serve different purposes and have a clear order of precedence:

### **Context**

> Purpose: provides dynamic input variables. Think of it as the model's working area — what the model is currently looking at.

**Notes:**

* Use the **Context** field to pass in the **query text**, **user input** or **data from earlier nodes**.
* Variables are supported, for example `${start.query}` or `${llm-nodeA.result}`, to make responses more personalized or context-aware.
* Short instructions can go here, but the Context field should hold **content** rather than rules about behavior.

### **System Prompt**

> Purpose: defines the model's behavior and persona. Think of it as this node's permanent job description.

**Notes:**

* Use it to define **who** the model is, **how** it should behave and **what** it should accomplish.
* Instructions in the System Prompt take **precedence** over instructions in the Context.
* Always define, explicitly:
  * The **persona** (for example product manager, analyst, mentor)
  * The **task goal** (for example write a report, explain code)
  * The **tone** (for example formal, friendly)
  * The **rules for using tools** (if tools are attached)

### **File Handling**

The **File handling** settings define how an Agent handles uploaded files in the Workspace. They are especially useful when the Agent needs to interpret, convert or extract file content in a conversation — a PDF, a DOCX or an image, for example.

<figure><img src="../.gitbook/assets/image (151).png" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="143">Option</th><th width="120">Visible to MCP Tool</th><th width="102">Visible to LLM</th><th>Description</th><th>Example use case</th></tr></thead><tbody><tr><td>Do not process</td><td>X</td><td>X</td><td>The file is uploaded but visible to neither the LLM nor MCP tools, and is not opened or parsed.</td><td>–</td></tr><tr><td>Tool processing only</td><td>O</td><td>X</td><td>The file is passed to MCP tools for processing but not given to the LLM.</td><td>For extracting data from a CSV or PDF without needing AI commentary.</td></tr><tr><td>Convert file to image</td><td>X</td><td>O</td><td>The file is converted to an image for the LLM to refer to only.</td><td>For scanned documents or visual material where the layout matters.</td></tr><tr><td>Convert to image and tool processing</td><td>O</td><td>O</td><td>The file is both converted to an image for the LLM and passed to MCP tools for processing.</td><td>For invoices or forms where both the visual structure and structured data need to be parsed.</td></tr></tbody></table>
