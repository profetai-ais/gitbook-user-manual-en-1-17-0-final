---
description: >-
  This page manages the API Keys the system needs. You can add, review and delete
  keys here, so services run securely and correctly.
---

# Key Management

## Page overview

The **Key Management** page lists the keys that have been created, with the following columns:

<figure><img src="../.gitbook/assets/image (756).png" alt=""><figcaption></figcaption></figure>

<table data-search="false"><thead><tr><th width="210">Column</th><th>Description</th></tr></thead><tbody><tr><td>Type</td><td>The key type (SERPER or LiteLLM, for example), which is the kind of service it belongs to</td></tr><tr><td>Name</td><td>The key's name, used to identify what this API Key is for</td></tr><tr><td>Key</td><td>The API Key value, masked for security</td></tr><tr><td>Tenant ID</td><td>The tenant identifier it belongs to</td></tr><tr><td>Expire Date</td><td>When the key expires</td></tr><tr><td>Creator</td><td>Who created it</td></tr><tr><td>Created Date</td><td>When it was created</td></tr><tr><td>Modified Date</td><td>When it was last updated</td></tr><tr><td>Actions</td><td>Available actions; currently delete (the trash icon)</td></tr></tbody></table>

## Adding a key

<figure><img src="../.gitbook/assets/image (757).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (758).png" alt=""><figcaption></figcaption></figure>

1. Click the "+" in the upper right to open the add key dialog, then complete the following:
2. Type: select the key type.
3. Name: enter a name for this API Key. A specific purpose (for example `litellm api key`) makes it easier to manage later.
4. API Key: enter the actual API Key.
   * The field is hidden by default.
   * Use the eye icon on the right to show or hide it.
5. Click **Ok** to save the key, or **Cancel** to discard it.

## Deleting a key

<figure><img src="../.gitbook/assets/image (759).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (760).png" alt=""><figcaption></figcaption></figure>

1. Click the trash icon in the **Actions** column at the far right of the row.
2. Confirm, and the key is removed from the list immediately.

### **Notes**

* **A deleted key cannot be recovered.**
* If the API Key is in use by the system or a process, deleting it may break that functionality.
* Confirm that the key is no longer referenced by any service or process before deleting it.
