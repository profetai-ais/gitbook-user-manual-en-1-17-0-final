# AI Studio Copilot

<figure><img src="../.gitbook/assets/image (586).png" alt=""><figcaption></figcaption></figure>

AI Studio Copilot is the built-in product assistant. It can help you look up features and how to use them, plan Agent solutions, troubleshoot problems, and assess whether a requirement is a good fit for AI Studio or AutoML.

Depending on the type of question, Copilot looks up the relevant product documentation, capability data and known issues, then turns them into instructions you can act on. If the available information is not enough to be certain, Copilot asks for the details it needs, or states clearly that an administrator or consultant has to confirm.

> Copilot provides guidance, diagnostics and recommendations. It does not change system settings or make changes on your behalf.

## Opening Copilot

<figure><img src="../.gitbook/assets/image (587).png" alt=""><figcaption></figcaption></figure>

1. Click the blue **Copilot** icon in the lower-right corner of the screen.
2. Enter your question in natural language in the input box.
3. If your question relates to a specific page, Agent or error, include the feature you are in, what you are trying to do, and the full error message, so you get a more precise answer.

## What you can ask

Copilot chooses how to handle a question based on what you ask. Focusing on one main question at a time makes the answer easier to apply directly.

### Features and how-to questions

Good for asking what a feature does, where to find it, how to set it up, and what permissions and prerequisites it needs. You can also ask how two features differ.

For example:

* How do I attach a Skill to an Agent?
* What is the difference between Knowledge Base and a DB MCP Tool?
* Where do I configure an Agent's Memory?
* What is Canvas and how do I open it?
* What permissions do I need to use a particular feature?

Copilot compiles the steps from the product manual. When the documentation includes the matching screens, it may also provide screenshots and sources so you can compare them with the actual interface.

### Solution recommendations

When you describe what you want to achieve, Copilot can help you work out which features fit, and lay out the recommended combination, the order to configure things in, the prerequisites and the limitations.

For example:

* I want to build an Agent that reads our company SOPs and answers questions about them. Which features should I use?
* I want an Agent to classify the question and hand it off to different specialized Agents. How should I design that?
* I need to query exact records in a database. Should I use Knowledge Base or an MCP Tool?

If there is not enough information, Copilot may first ask about your data types, environment, current settings or external integration needs. If there is no solid product basis for an answer, it says so instead of assembling an unverified combination of features.

### Problem diagnosis

Good for error messages, features that do not work, buttons that do not appear, failed runs and unexpected results.

For example:

* Why can't I see a certain feature or button?
* My Workflow failed. How can I investigate?
* An API Tool returns `401 Unauthorized`. What should I do?
* The Agent did not find the content in my Knowledge Base. What might be wrong?

Copilot first checks known issues and the product documentation, then offers possible causes and steps to take. If it finds a matching Known Issue, the answer may include the issue number, the expected behavior, the current behavior and any available workaround. If the problem involves account status, permissions or live environment information, Copilot tells you to confirm with an administrator or the relevant team.

### Feasibility and product choice

Good for asking whether something is possible, whether to use AI Studio or AutoML, whether a capability is native, and whether an external system is required.

For example:

* Should this requirement use AutoML or AI Studio?
* Can AI Studio connect to our existing database or API?
* Can this process be done with an Agent alone, or does it need an MCP Tool or another external system?
* Is it possible to combine document Q&A, data lookup and external actions in a single process?

The answer covers the feasibility verdict, the reasoning, a recommended implementation, the prerequisites to confirm first, and suggested next steps. If a core capability is outside the currently confirmed product scope, Copilot flags that it needs to be confirmed with a consultant.

## How to provide more complete information

The clearer the background you give, the easier it is for Copilot to find the right documentation or narrow down the problem.

| Question type             | Information to provide                                                                                                       |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| **How-to question**       | The module or page you are on, what you want to do, and how far you have got.                                                 |
| **Error diagnosis**       | The full error code and message, the page it happened on, the action that triggered it, and the expected and actual results. Keep the error text as it is. |
| **Solution planning**     | The goal, the form your data takes, the Agents / Knowledge Bases / Tools you already have, and whether external systems need to be connected. |
| **Feasibility assessment**| The scope, the required features, existing data, the state of external systems and APIs, and the expected output or criteria.  |

If key details are missing, Copilot usually asks a few necessary questions first. Once you provide them, you can continue in the same conversation.

## Asking Copilot about an error <a href="#yu-dao-cuo-wu-shi-xun-wen-copilot" id="yu-dao-cuo-wu-shi-xun-wen-copilot"></a>

When an Agent fails to respond and shows an error message, you can ask Copilot to analyze the cause directly, without copying the error message yourself.

> Note:
>
> * Each click of the ask button opens a new Copilot conversation. If Copilot is answering another question, the system asks whether to interrupt the current answer.
> * Copilot's suggestions are for reference only. Some errors — such as a session timeout, insufficient permissions or a system fault — still need to be confirmed with an administrator or technical support.

### An error during a conversation

<figure><img src="../.gitbook/assets/image (584).png" alt=""><figcaption></figcaption></figure>

1. Hover over the error message.
2. Click the ask button. Copilot opens on the right side of the screen with your original question and the error message filled in automatically.
3. Copilot analyzes the possible causes and suggests what to do.
4. After reading the suggestions, go back to the conversation, make the adjustments and try again.

> Note:
>
> This also works in the debug preview on the Agent settings page.

### Error messages in the lower left

<figure><img src="../.gitbook/assets/image (583).png" alt=""><figcaption></figcaption></figure>

1. Hover over the error message.
2. Click the ask button. Copilot opens on the right side of the screen with your original question and the error message filled in automatically.
3. Copilot analyzes the possible causes and suggests what to do.
4. After reading the suggestions, go back to the original screen, make the adjustments and try again.

> Note: Error messages stay on screen longer than ordinary notifications so that you have time to click the ask button. They close automatically once the time is up.

### An MCP Server is offline

<figure><img src="../.gitbook/assets/image (585).png" alt=""><figcaption></figcaption></figure>

1. Hover over the offline MCP Server.
2. Click the info button.
3. Click the ask button. Copilot opens on the right side of the screen with your original question and the error message filled in automatically.
4. Copilot analyzes the possible causes and suggests what to do.
5. After reading the suggestions, go back to MCP, make the adjustments and try again.

### A run fails in Job Management

<figure><img src="../.gitbook/assets/image (589).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (590).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (591).png" alt=""><figcaption></figcaption></figure>

1. Select the Task with the error status.
2. Click the info button.
3. Click the ask button. Copilot opens on the right side of the screen with your original question and the error message filled in automatically.
4. Copilot analyzes the possible causes and suggests what to do.
5. After reading the suggestions, go back to that step, make the adjustments and try again.

## Notes

* Copilot's answers are based on the product documentation, capability data and known issues currently available to it. A capability that is not documented is not assumed to be supported.
* Database, external API and MCP integrations require a reachable service, appropriate permissions, valid credentials and a clearly defined data format.
* Questions about a personal account, Workspace permissions or live system status may still need to be checked by an administrator.
* Pricing, SLA, roadmap, version-specific limitations, regulatory compliance and formal commitments must be confirmed through official information or a consultant.
* For complex or high-risk requirements, we recommend narrowing the scope into a POC first, then deciding whether to expand the rollout based on the results.
* AI Studio Copilot uses Workforce runtime slots. When all Workforce slots are in use, a request may be queued until a slot is released.
