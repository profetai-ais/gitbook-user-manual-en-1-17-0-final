---
description: >-
  AI Studio provides two levels of access control, so you can flexibly define
  who can access a given feature list and who can act on the individual items
  inside it.
---

# AI Studio Permission Architecture

## Permission architecture

<figure><img src="../.gitbook/assets/image (508).png" alt=""><figcaption></figcaption></figure>

### Feature level (Root)

Controls who can use and manage a whole category of features — for example the Agent list, the Knowledge Base list or the Template list. This level determines whether you can enter the feature, create new items, and manage the member list for that feature.

Root view permissions depend on the AI Studio role configuration. For details, see [AI Studio Roles and Permissions](ai-studio-jue-se-yu-quan-xian-shuo-ming.md).

### Item level (Object)

Controls the permissions of each individual item inside a feature — for example one specific Agent, one specific knowledge base or one specific template. This level lets you assign member roles per item, deciding who can edit it, who can only use it, and who can manage its members.

Object view permissions depend on the Root role configuration. For details on Root roles, see the **list role permissions** sections in [Module Permission Roles](quan-xian-gong-neng-jie-shao.md).

> Note: By default, only roles with management permissions can enter the corresponding feature and perform management actions. If you cannot see certain features or perform certain actions, check with your administrator whether you have been granted permissions at both the feature level and the item level.

## How permissions are evaluated

<figure><img src="../.gitbook/assets/image (509).png" alt=""><figcaption></figcaption></figure>

The system first evaluates the user's Root permission for the feature, then uses the user's Root role to decide whether Object permissions need to be evaluated as well.

* If the user is a **List Admin** for the feature, they can manage the objects in that feature and can add, edit and delete them even without Object permissions on the individual objects.
* If the user is a **List User** for the feature, Object permissions still determine which objects they can access and act on.
* If the user has no Root permission for the feature, they cannot open the feature page or act on any object in it.

### Notes

What a user can actually see and do varies with the Root and Object permission settings. If a user cannot see a particular feature or object, confirm that they have the Root permission for that feature and that the object has been granted the corresponding Object permission.

If a user needs to manage every object in a feature, set them as the Root Admin for that feature. If they only need to work with specific objects, grant them Object permissions instead.

After permissions are changed, some pages may need to be refreshed, or reopened, before the latest permission results are shown.

## Root permissions

<figure><img src="../.gitbook/assets/image (594).png" alt=""><figcaption></figcaption></figure>

Root permissions are the outermost level of control for a module. They define the overall scope of what a user can do within a feature. Root permissions are usually divided into the following roles:

* **List Admin**
* **List User**

What each Root role can do varies by feature design.

A user must have the Root permission for a feature in order to open its page or use its main actions — for example to enter Agent, Knowledge Base, Template or another feature module.

Of the two, **List Admin** has the highest management permission within the feature. When a user is the List Admin of a feature, they can add, edit and delete objects in that feature even without being granted specific Object permissions.

## **Object permissions**

<figure><img src="../.gitbook/assets/image (595).png" alt=""><figcaption></figcaption></figure>

Object permissions control which individual objects a user can access and act on within a feature.

A single feature may contain many objects, such as different Agents, knowledge bases, templates or other items. When a user is not the List Admin of the feature, the system uses each object's Object permissions to determine whether the user can view, use, edit or manage it.

## Syncing AI Studio and Root permissions

After a user signs in, the system automatically fills in list permissions to match the AI Studio account's current permissions.

For example, an account with the **AI Studio Domain User** role automatically receives **List User** permissions for Agent, Knowledge Base, Capability (Skill, MCP), Template (Workflow, Prompt) and Analytics (Report) after signing in.

This sync **only runs at sign-in and only fills in permissions that are missing**. It **does not affect existing list permissions**, and if the account's AI Studio permissions change later, the automatic sync is not triggered.
