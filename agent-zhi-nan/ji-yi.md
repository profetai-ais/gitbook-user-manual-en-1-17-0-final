---
description: >-
  Memory lets you build reusable memory content for an Agent, so that it can
  refer to predefined background information, use cases and procedures when
  performing tasks or answering questions.
---

# Memory

<figure><img src="../.gitbook/assets/image (702).png" alt=""><figcaption></figcaption></figure>

On an Agent's Memory page you can see the list of memories that have been created, and identify what each one is for from its enabled state, name, description and use case. Memories can hold specific procedures, decision rules, prerequisites, steps or things to watch out for, which helps the Agent keep its logic consistent in later interactions.

### Cited

<figure><img src="../.gitbook/assets/memory-cited-column.png" alt=""><figcaption></figcaption></figure>

The **Cited** column in the memory list shows how many times the Agent has cited each memory. Use it to see which memories are used often and which have not been cited for a long time and could be disabled or merged.

## **Where Agent memories come from**

Agent memories are extracted from **all conversations with that Agent**. The system analyzes the conversations automatically, identifies knowledge, preferences and procedures worth keeping long term, and organizes them into manageable memory entries for the Agent to keep using.

## Agent memory settings

Memory extracts information from past conversations so the Agent can respond more consistently later on. The settings are behind the memory gear icon on the Agent's home page.

<figure><img src="../.gitbook/assets/image (701).png" alt=""><figcaption></figcaption></figure>

### Memory

Memory compiles reusable information from conversations so the Agent can cite relevant memories and conversation summaries later.

<table><thead><tr><th width="193">Setting</th><th>What it does</th><th>Values and system behavior</th></tr></thead><tbody><tr><td>Memory citation</td><td>Controls whether the Agent can cite memories and conversation summaries in its responses.</td><td>When enabled, the system first processes existing conversations, then processes new ones at the time you set. When disabled, the Agent does not cite this content in its responses.</td></tr><tr><td>Automatically optimize memory</td><td>Controls whether the system extracts and organizes reusable information from conversations automatically every day.</td><td>When enabled, the system runs daily at the <strong>memory extraction time</strong>. When disabled, no daily processing takes place.</td></tr><tr><td>Memory extraction time</td><td>Sets the time of day the system organizes memories automatically.</td><td>Set it with the time picker; the example on screen is <code>02:00</code>. Only takes effect when <strong>Automatically optimize memory</strong> is enabled.</td></tr><tr><td>Extraction instructions</td><td>Specifies what the system should prioritize when compiling memories from conversations.</td><td>Enter extraction principles suited to the Agent's purpose. If left blank, the system uses its default rules.</td></tr><tr><td>Instructions (optional)</td><td>Enter specific extraction requirements.</td><td>Free text, for example: "Only extract MCP configuration procedures."</td></tr></tbody></table>

**Memory citation** controls whether the Agent can use memories; **Automatically optimize memory** controls whether the system regularly compiles and updates memories from new conversations. They serve different purposes.

{% hint style="info" %}
Once **Memory citation** or **Automatically optimize memory** is turned on, this Agent uses Workforce slots instead. Workforce usually has a lower slot limit, so requests may need to queue when usage is high. See [Workforce Monitor](../fen-xi-zhi-nan/workforce-jian-kong.md#assistant-yu-workforce-de-cha-yi).
{% endhint %}

Extraction instructions only affect which content the system selects as a memory; they do not change how the Agent answers. When you are done, click **Save** to apply the changes.

* Example instruction: prioritize technical settings, procedures and confirmed decisions related to the current project; ignore small talk and transient information.

## Viewing the processing log

The **Processing Log** tab on the Memory page lists the runs of each memory optimization, so you can see which conversations the system extracted or adjusted memories from.

1. Open the Agent's Memory page and switch to the **Processing Log** tab.
2. The list shows each optimization run.
3. Expand a run to see each conversation (Session) processed in it.
4. Expand a single conversation to see the processing details. Optimization and conflict resolution show different content.

## Creating an Agent memory manually

<figure><img src="../.gitbook/assets/image (703).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (704).png" alt=""><figcaption></figcaption></figure>

1. Open the Agent page and click **Memory** in the submenu on the left.
2. Click the **Create** button in the upper right.
3. Fill in the memory's basic information:
   * Name: the memory's name.
   * Description: what the memory is about.
   * Use case: the situations this memory applies to.
   * Content: the detailed content, which can be formatted with Markdown.
4. Check the content and click **Create** to finish.

## Viewing the details of an Agent memory

<figure><img src="../.gitbook/assets/image (706).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (705).png" alt=""><figcaption></figcaption></figure>

1. Open the memory list.
2. Click the name of the memory you want to see.
3. A details panel opens on the right.
4. You can see the memory's name, enabled state, description, use case and full content. If the content is long, scroll in the panel on the right.

## Merging memories

<figure><img src="../.gitbook/assets/image (712).png" alt=""><figcaption></figcaption></figure>

When several memories contain the same or related information, use **Merge memories** to combine them.

1. Select two or more memories to merge.
2. Check the number of selected items shown in the toolbar.
3. Click the **Merge memories** button.
4. The system merges the selected memories and updates the memory list when it is done.

> We recommend merging memories with similar content or on the same topic, rather than combining information that serves different purposes.

## Enabling and disabling Agent memory

### How Agent memory is enabled

Memory has both an overall toggle and a per-memory enabled state.

<figure><img src="../.gitbook/assets/image (707).png" alt=""><figcaption></figcaption></figure>

When the toggle is on, this Agent can use memory. You can still enable or disable individual memories in the memory list.

When the toggle is off, this Agent does not use memory. Even if memories exist in the list, the Agent does not apply them.

### Enabling and disabling an individual Agent memory

<figure><img src="../.gitbook/assets/image (708).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (709).png" alt=""><figcaption></figcaption></figure>

In the memory list, the **Enabled** column shows whether an individual memory is enabled. When the overall memory toggle is on, only the enabled memories are used as reference when the Agent responds or handles a task.

You can disable a memory you do not currently need, which keeps its content without letting the Agent apply it, and enable it again later.

### **How to confirm that an Agent memory was used**

<img src="../.gitbook/assets/unknown (1).png" alt="" height="312" width="602">

1. Ask a question in a test conversation and look at the Agent's response log.
2. If PROFETAI\_use\_agent\_memory appears, the Agent called the memory feature.
3. A green check mark means the memory tool ran successfully.
4. Expand the tool block and look at **Output** to see the memory data that was actually used.

If the memory tool does not appear, that conversation did not use a stored memory.

You can also check the **Cited** column in the memory list to see how many times each memory has been cited in total.

## Turning an Agent memory into a skill

When the content of an Agent memory is already well organized and needs to be reused, you can turn it into a skill, so that other Agents or workflows can use the same capability without building it again.

### When to use it

We recommend turning a memory into a skill when:

* The procedure is finished and its content is stable.
* The work is performed repeatedly.
* You want several Agents to share the same capability.
* You want to standardize experience or knowledge.

### Steps

<figure><img src="../.gitbook/assets/image (710).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (711).png" alt=""><figcaption></figcaption></figure>

1. Open **Agent Memory** and select the memory you want to convert.
2. Click **Convert to skill**.
3. The skill name defaults to the memory title. Select a category for the skill; if none fits, click the "+" next to it to add one.
4. Click convert.
5. When the conversion succeeds, a message appears. Click the skill name in it to open the skill in a new tab, or find it in the **Skill** list and apply it to other Agents.

### Notes

* Converting creates a new skill; **the original memory is not deleted**.
* Later changes to the memory and the skill **are not synced**.
