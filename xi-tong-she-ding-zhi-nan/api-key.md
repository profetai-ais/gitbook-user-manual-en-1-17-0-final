# API Key

## Introduction

An API Key lets you create a dedicated key so external systems can call the open APIs AI Studio supports. With an API Key, an external program, integration service or third-party tool can make API calls as the user the key is bound to, without signing in with an account and password. On this page you can create a new API Key and open the API documentation to see the specifications available.

Every API Key is bound to the user who created it, and the system uses that user's permissions to determine which APIs can be accessed.

{% hint style="info" %}
API Key is under **System Setting → API Key** and is available to AI Studio Admins only; AI Studio Domain Users and AI Studio Users cannot create API Keys. The former entry point in the avatar menu in the upper right has been removed.
{% endhint %}

<figure><img src="../.gitbook/assets/image (75).png" alt=""><figcaption></figcaption></figure>

## API Key settings

Open API Key and click the generate button to generate a key.

<figure><img src="../.gitbook/assets/image (76).png" alt=""><figcaption></figcaption></figure>

> Note: The full API Key is shown only once, when it is created. For security, the system does not show it in full again and cannot retrieve the original key. If you lose it, delete the key and create a new one.\
> Each user can have at most 1 API Key. To generate a new one, delete the existing key first.

### Managing API Keys

Once you have created an API Key, you can see all the keys you created. To keep them safe, the list shows only the masked form, for example:

```
gak_abc*******xyz
```

Once an API Key is disabled or deleted, external systems can no longer use it for API calls. If a key has an expiry date, the system invalidates it automatically when that date passes.

> Note: Do not expose an API Key in a public environment such as front-end code, a public Git repository or an unprotected document. If you suspect a key has been leaked, disable or delete it immediately and create a new one.

## API documentation

<figure><img src="../.gitbook/assets/image (77).png" alt=""><figcaption></figcaption></figure>

In the API documentation block, click **Open API documentation**. It shows the available API specifications, and the Swagger UI lets you see API paths and parameters and test requests.

> Note: Some APIs need the Knowledge Base ID (`kbId`) or the dataset ID (`datasetId`). You can view and copy these in the edit window of the corresponding item; see [Managing the Knowledge Base - Viewing and copying the Knowledge Base ID](../zhi-shi-ku-zhi-nan/guan-li-zhi-shi-ku.md#cha-kan-yu-fu-zhi-zhi-shi-ku-id).

## Usage history

<figure><img src="../.gitbook/assets/image (79).png" alt=""><figcaption></figcaption></figure>

On the usage history tab you can review an API Key's usage. This helps you track how external systems are calling the API and check for unusual requests. You can also query the calls made within a specific date range.
