# System Notification

System notifications bring together the messages sent by the platform and by each product — for example schedule run results, items that need a user response, and system announcements. Notifications are kept in the notification center, and some can also appear as a pop-up so you can read them, or respond, without leaving the page you are on.

## Opening the notification center

<figure><img src="../.gitbook/assets/image (80).png" alt=""><figcaption></figcaption></figure>

1. Click the notification icon on the right side of the page.
2. When the notification panel opens, you can see the notifications you received most recently.
3. Click any notification to open its details.
4. To browse the full notification history, click **View All** at the bottom of the panel.

## Notification categories

The notification center has two categories:

### Personal notifications

<figure><img src="../.gitbook/assets/image (577).png" alt=""><figcaption></figcaption></figure>

Shows notifications sent directly to the current user, such as:

* Schedule triggered or run completed notifications
* Messages produced while an Agent is running
* Items that need a user response or decision
* Personal reminders sent by each product

### System announcements

<figure><img src="../.gitbook/assets/image (578).png" alt=""><figcaption></figcaption></figure>

Shows announcements published by the system, such as service notices, system maintenance and version updates.

## Notification content

A notification may contain the following information:

<table data-search="false"><thead><tr><th>Item</th><th>Description</th></tr></thead><tbody><tr><td>Source product</td><td>Which product or service sent the notification, for example AI Studio, Portal or MCPHub.</td></tr><tr><td>Notification time</td><td>The date and time the notification was created or sent.</td></tr><tr><td>Title</td><td>The main event or the item that needs attention.</td></tr><tr><td>Message source</td><td>Which Agent, schedule or feature produced the message.</td></tr><tr><td>Status</td><td>Whether the notification needs action, for example "Pending" or "Expired".</td></tr><tr><td>Details</td><td>The run result, the message content, or the response options available. The content supports formatted display (HTML), such as headings, lists, tables, and links.</td></tr></tbody></table>

## Pop-up reminders

<figure><img src="../.gitbook/assets/image (579).png" alt=""><figcaption></figcaption></figure>

When **Pop-up Reminder** is enabled, notifications can appear as a pop-up while you are working in the system.

A pop-up reminder may include:

* The notification title
* When it occurred
* The source or sender
* The run result or message content
* Response options you can act on directly

Turning off pop-up reminders only stops the pop-ups; it does not delete notifications. You can still see the messages you received in the notification center.

If you dismiss a pop-up, you can reopen the notification content from the notification center later.

## Schedule notifications

When a schedule reaches its configured time and is triggered, the system creates a notification. It can show the schedule name, the run time and the run result.

To view a schedule notification:

1. Click the notification icon to open the notification center.
2. Find the schedule notification.
3. Click it to see the schedule's run result and details.
4. When you have finished reading, click the **×** in the upper right to close the window.

If pop-up reminders are enabled, schedule notifications may also appear directly on the current page.

## Notifications that need a response

When a schedule, an Agent or another feature needs a decision from you, it sends a notification that needs a response. For example, when a workflow reaches a [Human Input](../agent-zhi-nan/gong-zuo-liu-cheng-jie-dian.md) node, the confirmer receives this kind of notification.

Taking the Human Input node as an example, the notification contains:

<table data-search="false"><thead><tr><th width="160">Item</th><th>Description</th></tr></thead><tbody><tr><td>Title</td><td>Shows the Agent's icon and name, followed by "needs your response".</td></tr><tr><td>Message</td><td>Shows the message set in the node.</td></tr><tr><td>Action buttons</td><td>Laid out the same way as on the card in the conversation; scroll to see more when there are many options.</td></tr><tr><td>Back to conversation</td><td>In the top-right corner; click it to return to the original conversation. The left-side navigation menu remains visible.</td></tr></tbody></table>

To respond:

1. Open the notification that needs a response.
2. Read the message in the notification.
3. Click one of the actions to send your response.
4. Once the system receives your choice, it continues the process accordingly.

When you click "Back to conversation", users with permission for the Agent enter the original conversation; users without permission see "No permission" but can still respond by clicking an action in the notification.

Notifications that need a response are not always created by a schedule. They can also appear while an Agent is running, or be triggered by a request for input in an ordinary conversation.

For now, notifications only support choosing from preset options; entering free text or filling in a form is not supported yet.

## The difference between ordinary and pending notifications

| Notification type     | How it is used                                                                                                                                     |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| Ordinary notification | Delivers a run result or message content. Open it to see the details; no further action is needed.                                                   |
| Pending notification  | <p>Shows the "Pending" status and needs you to respond or complete a specified action before the process continues.<br>"Expired" means the deadline for that action has passed.</p> |

## Notes

* Notification content and the available actions vary by source product and feature.
* After turning off pop-up reminders, you can still see the notifications you received in the notification center.
* If a notification shows "Pending", open its details to check whether a response is needed.
* For now, notifications only support the preset options; filling in a form directly is not supported.
* Before clicking a notification, check the source product, the time it was sent and the message source, so you do not act on the wrong one.
