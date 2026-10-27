---
description: This page explains how to work with Root permissions and Object permissions.
---

# Permission Actions

## **Root permissions** <a href="#root-quan-xian" id="root-quan-xian"></a>

### **Where to find it**

Root permission settings are under the **More** button in the upper-right corner of the module. Click it to open the permission management window.

<figure><img src="../.gitbook/assets/image (614).png" alt=""><figcaption></figcaption></figure>

### Page overview

<figure><img src="../.gitbook/assets/image (615).png" alt=""><figcaption></figcaption></figure>

| Item | Action            | Description                                                                                           |
| ---- | ----------------- | ----------------------------------------------------------------------------------------------------- |
| 1    | Select User       | Search by name or account to add a user                                                               |
| 2    | Select Permission | Select the list permission to assign                                                                  |
| 3    | Added Users       | View the users who have been added and their permission settings; adjust permissions or remove a user |

### **Add a member**

<figure><img src="../.gitbook/assets/image (616).png" alt=""><figcaption></figcaption></figure>

1. Enter a keyword to search for the user you want to add.
2. Set the permission to grant.
3. Click **Add** to finish. The permission takes effect after the other user refreshes the page.

### **Change a member's permission**

<figure><img src="../.gitbook/assets/image (617).png" alt=""><figcaption></figcaption></figure>

1. Find the user whose permission you want to change.
2. Click the drop-down menu on the right and change the permission.

### **Remove a member**

<figure><img src="../.gitbook/assets/image (618).png" alt=""><figcaption></figcaption></figure>

1. Find the user you want to remove.
2. Click the drop-down menu on the right and select **Remove**.

## Object permissions

Object permissions can work differently from feature to feature. The two common models are role-based permissions and access permissions.

### **Where to find it**

Permission settings live inside each object of a module. Click the object you want, then open the **Permission** tab on its detail page to see the permission management page. The Agent module is used as the example here.

<figure><img src="../.gitbook/assets/image (619).png" alt=""><figcaption></figcaption></figure>

### Role permissions <a href="#jue-se-quan-xian" id="jue-se-quan-xian"></a>

Role permissions define what a user can do based on their role. Each object can have 2 to 3 permission roles, and the creator can grant access to other users through **Permission**. Users with higher permissions can usually manage the object's settings, adjust its content or maintain who has access; users with lower permissions may only be able to view or use the object.

Common cases include:

* Can manage the object
* Can edit the object
* Can view or use the object

> Note: The actual role names and what each role can do vary by feature design. For role definitions, see [Module Permission Roles](quan-xian-gong-neng-jie-shao.md).

### Page overview

<figure><img src="../.gitbook/assets/image (620).png" alt=""><figcaption></figcaption></figure>

<table data-search="false"><thead><tr><th>Item</th><th>Action</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Edit Table</td><td>Lets you change how the table is displayed</td></tr><tr><td>2</td><td>Refresh</td><td>Click to refresh the list</td></tr><tr><td>3</td><td>Filter</td><td>Advanced filtering for specific content</td></tr><tr><td>4</td><td>Bulk Delete</td><td>Once items are selected, the delete button appears in the upper left so you can delete multiple items</td></tr><tr><td>5</td><td>Search Field</td><td>Search by name</td></tr><tr><td>6</td><td>Invite</td><td>Invite an organization or a member</td></tr><tr><td>7</td><td>Actions</td><td>Transfer your role or delete the selected user</td></tr></tbody></table>

#### **Add a member**

<figure><img src="../.gitbook/assets/image (621).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (622).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (623).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (624).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (625).png" alt=""><figcaption></figcaption></figure>

1. Click **Add** to open the **Add Member** dialog.
2. Use the input field to search for an organization or a user.
3. Select the corresponding permission.
4. There are two ways to select an organization or user:
   * Click to search by organization.
   * Enter a keyword to bring up matching organizations and users, then click the level button on the right to confirm the role's level.
5. After selecting the target organization or user, click the tag to open the view menu and see the organization level and all users in that role.
6. Click the **Add** button to finish the invitation.

> Note: Organizations and users you have selected are shown as checked in the list, and you can also select the whole organization list at once. Selected items appear in the input field, up to three lines; anything beyond that is shown as "+N".

#### **Change a member's permission**

<figure><img src="../.gitbook/assets/image (626).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (627).png" alt=""><figcaption></figcaption></figure>

1. Find the organization or user whose permission you want to change and click its edit button.
2. Change the permission.
3. Click **Save** to finish.

#### **Transfer ownership**

<figure><img src="../.gitbook/assets/image (629).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (630).png" alt=""><figcaption></figcaption></figure>

1. Find the user you want to transfer ownership to and click the transfer permission button.
2. Confirm the user's information.
3. Click **Transfer** to finish.

> Note:
>
> 1. Ownership can only be transferred to a user. You cannot transfer ownership to an organization.
> 2. After the transfer, the object's owner and creator automatically become the new user, while your own object permissions stay as they were before the transfer.

#### **Remove a member**

<figure><img src="../.gitbook/assets/image (631).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (632).png" alt=""><figcaption></figcaption></figure>

1. Find the organization or user you want to remove and click its remove button.
2. Confirm the removal and click the remove button again.

### Access permissions <a href="#cun-qu-quan-xian" id="cun-qu-quan-xian"></a>

Access permissions can be granted to an organization or to individual users. If you grant them to an organization, every user in that organization can use the data. The knowledge base dataset is used as the example here.

{% hint style="info" %}
In AI Studio, the objects that currently have access permission settings are the **knowledge base dataset** and the **MCP Tool in MCP**.
{% endhint %}

#### **Add a member**

<figure><img src="../.gitbook/assets/image (633).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (634).png" alt=""><figcaption></figcaption></figure>

1. In the **knowledge settings menu**, click _Dataset Permission_.
2. Click the button to add permissions to datasets in bulk.
3. In the **Dataset** area, select the files you want to set permissions for.
4. In the area on the right, click the **Organization** tab and select the organization levels to grant permissions to.
5. In the area on the right, click the **User** tab and select the users to grant permissions to.
6. Use the **user menu** to search for the users you want to add.
7. When you have finished changing organizations and users, click **OK** to keep the settings.

#### **Remove a member**

<figure><img src="../.gitbook/assets/image (635).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (635).png" alt=""><figcaption></figcaption></figure>

1. Click the edit button on the dataset you want to change.
2. Select the organization or user you want to remove and click its remove button.
3. Click **Save** to finish.
