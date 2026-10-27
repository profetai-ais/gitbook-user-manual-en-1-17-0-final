# Tag Management

## Introduction

Tag Management helps you classify and manage items in the system with tags. Adding tags to items makes them easier to identify, filter and find in a list. On this page you can review, create, edit and delete tags in one place, and see which feature module each tag belongs to.

<figure><img src="../.gitbook/assets/image (745).png" alt=""><figcaption></figcaption></figure>

## Creating a tag

<figure><img src="../.gitbook/assets/image (746).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (747).png" alt=""><figcaption></figcaption></figure>

1. Open **Tag Management** under **System Setting**.
2. Select the module to add the tag to.
3. Click the **Add** button in the upper right.
4. Enter the tag name. You can also click the button on the right to add multilingual labels; see [Multilingual settings](biao-qian-guan-li.md#duo-guo-yu-yan-she-ding).
5. Check the content and click save or create. The tag then appears in the Tag Management list.

### Multilingual settings <a href="#duo-guo-yu-yan-she-ding" id="duo-guo-yu-yan-she-ding"></a>

<figure><img src="../.gitbook/assets/image (748).png" alt=""><figcaption></figcaption></figure>

1. Click the globe button to translate automatically. You can also edit the content manually.
2. When the automatic translation is done, click **OK** to save.

> Note: The large language models available in the **Model** menu depend on the configuration of your installed environment. The options shown in this manual are for reference only.

### Notes

* Tags are mainly for classifying, filtering and managing items. Agree on a naming convention before creating tags, so a module does not end up with several similarly meaning tags under different names, which makes management harder.
* Duplicate tag names are not allowed within the same feature module, but the same name can be used in different modules. Agent and Knowledge Base, for example, can each have a tag with the same name, and the two belong to different modules.
* Tag names support multiple languages, and a search uses the system's current language. If you switch languages, what is displayed or found may differ accordingly.

## Deleting a tag

When you delete a tag that other data uses, the system shows a confirmation dialog with two options:

* **Replace with another tag**

With **Replace with another tag**, you specify a new tag to replace it. Once confirmed, all data that referenced the original tag references the new one instead. This cannot be undone.

* **Do not replace; remove all associations**

With **Do not replace; remove all associations**, the system removes the association between the tag and all data. The data itself is not deleted, but it no longer carries this tag. This cannot be undone.

<figure><img src="../.gitbook/assets/image (751).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (752).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (753).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (754).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (755).png" alt=""><figcaption></figcaption></figure>

1. Open the **Tag Management** page.
2. Find the tag you want to delete and click the delete icon on the right of its row.
3. Choose how to handle it:
   * Select **Replace with another tag** and specify the new tag.
   * Or select **Do not replace; remove all associations**.
4. Click **Continue**.
5. The system shows a confirmation dialog for your choice. Check it and click **Replace** or **Delete** to finish.

### Notes

* Deleting a tag or replacing its associations cannot be undone. Before doing either, confirm whether the tag is still used by other data and whether it should be replaced with another tag first.
* With **Replace with another tag**, all data referencing the original tag references the new one. With **Do not replace; remove all associations**, all data referencing it loses that tag.
* Deleting a tag only removes the tag or its associations; it does not delete the feature modules or other data the tag was applied to.
