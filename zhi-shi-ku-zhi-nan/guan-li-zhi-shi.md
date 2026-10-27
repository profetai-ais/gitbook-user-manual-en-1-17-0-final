---
description: Click a knowledge card on the Knowledge Base page to open its settings page.
---

# Managing Knowledge

## **Dataset**

The **Dataset** settings page is where you upload and manage files. AI Studio supports:

* Long-form text (TXT, Markdown, DOCX, HTML, JSONL, and PDFs that are not pure images)
* Structured data (CSV, Excel and so on)

<figure><img src="../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

<table data-search="false"><thead><tr><th width="80">Item</th><th width="180">Action</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Edit Table</td><td>Lets you change how the table is displayed</td></tr><tr><td>2</td><td>Refresh</td><td>Click to refresh the table</td></tr><tr><td>3</td><td>Filter</td><td>Filter content by column</td></tr><tr><td>4</td><td>My List</td><td>When enabled, shows only the data you created</td></tr><tr><td>5</td><td>Bulk Download</td><td>Select several items and download them at once</td></tr><tr><td>6</td><td>Delete</td><td>Once datasets are selected in the list, the delete button appears; click it to delete the selected datasets</td></tr><tr><td>7</td><td>Search</td><td>Filter by keyword</td></tr><tr><td>8</td><td>Add / Import</td><td>Upload files, or create an empty dataset</td></tr><tr><td>9</td><td>Actions</td><td>Edit or delete the dataset</td></tr></tbody></table>

## **Adding a dataset**

### Adding one manually

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

1. Click **Dataset** in the Knowledge Base menu.
2. Click the **Add** button in the upper right and select **+ Dataset**.
3. Enter a title.
4. Choose whether to enable automatic description generation.
   *   **With "Generate description automatically" on**

       The first time content is added to the dataset, the system schedules the generation of a dataset description. Adding, removing or changing the dataset's content later reschedules it, so the description stays consistent with the current dataset. Because it is handled by a scheduled job, the update may take a while after a change.
   *   **With "Generate description automatically" off**

       A **Description** field appears, where you can enter or edit the dataset description yourself. The system does not update this field when the dataset's content changes later.

### Importing files

<figure><img src="../.gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

1. Click _Dataset_ in the **knowledge settings menu**.
2. Click the **Add / Import** button and select _Import files_.
3. Click the **upload area** to open the system dialog, select the files to upload, and then click _Next_.
4. Choose a processing mode: automatic or manual. With automatic processing you go straight to step 6; with manual processing you go to step 5.
5. For data processing, choose a chunking strategy under **File processing** on the left, then click _Generate chunks_ to see a preview of the resulting data on the right. Confirm the processing and click _Next_.
6. Check the content once more and click **Upload** to upload the files.
7. The page returns to the dataset list. The data is ready to use once the file status column shows **Completed**.

### File upload limits

To keep processing performance and index quality up, importing files into a dataset has the following limits:

| Item                        | Limit                    |
| --------------------------- | ------------------------ |
| Files per import            | Up to **100** files      |
| Maximum size per file       | **300 MB**               |

Additional notes:

* If either limit is exceeded, the system shows a message and blocks the upload. Reduce the number of files or split them and import again.
* For large documents (a long PDF or DOCX, for example), we recommend removing unnecessary images or appendices first, so processing does not take too long.

#### Preview and download access control

Preview and download permissions for source documents are controlled separately. Being able to see a source document or preview its content does not mean you can download the original file.

* Users with download permission: can download the original file from the dataset list, the chunk view or the source entry point, using the buttons shown.
* Users with preview permission only, or without download permission: can preview the source content where the interface allows it, but cannot obtain the original file through the source entry point. The download entry point may be hidden or unavailable.

To let others download dataset files, an administrator has to add the organizations or users under **Dataset Permission** for that dataset and save the settings. See Permission Actions - Object access permissions.

#### Troubleshooting: permission settings not displaying correctly

If permission details do not appear on the **Dataset Permission** page, a block is blank, or expanding it shows nothing, try the following in order:

1. Click **Refresh** to reload the list, or switch to another menu and back.
2. Confirm that the target file or dataset is selected in the **Dataset** area on the left.
3. Confirm that your account has a role that can manage this knowledge — AI Studio Admin, AI Studio Domain User, Knowledge Base List Admin, Knowledge Admin or Knowledge Editor. If not, ask your administrator for help.

### Supported dataset formats

Datasets accept many file formats, so you can pick the one that suits your data.

<table><thead><tr><th width="195">Data type</th><th>Supported formats</th></tr></thead><tbody><tr><td><strong>Text files</strong></td><td><code>.txt</code>, <code>.md</code>, <code>.csv</code>, <code>.json</code>, <code>.html</code>, <code>.htm</code></td></tr><tr><td><strong>Documents</strong></td><td><code>.pdf</code>, <code>.doc</code>, <code>.docx</code>, <code>.ppt</code>, <code>.pptx</code>, <code>.xls</code>, <code>.xlsx</code></td></tr><tr><td><strong>Images</strong></td><td><code>.jpg</code>, <code>.jpeg</code>, <code>.png</code>, <code>.gif</code>, <code>.bmp</code>, <code>.webp</code></td></tr><tr><td><strong>Audio</strong></td><td><code>.m4a</code>, <code>.mp3</code>, <code>.wav</code>, <code>.webm</code>, <code>.ogg</code>, <code>.aac</code>, <code>.flac</code></td></tr><tr><td><strong>Video</strong></td><td><code>.mp4</code>, <code>.mov</code>, <code>.avi</code>, <code>.mkv</code>, <code>.3gp</code></td></tr><tr><td><strong>Archives</strong></td><td><code>.zip</code>, <code>.tar</code>, <code>.gz</code>, <code>.tgz</code>, <code>.7z</code></td></tr></tbody></table>

> **Note**
>
> * Upload readable, complete files for the best knowledge extraction results.
> * When you upload an archive, the system extracts it automatically and imports the supported formats inside; unsupported files are skipped.
> * A file that is password-protected, corrupted or malformed may fail to import.

### Dataset status information

Click the status icon to open it. For details, see the Job Management page.

<figure><img src="../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>

## **Data processing when adding a dataset**

Two forms of processing are supported after a file is uploaded:

* **Direct chunking**: chunks according to the options you choose.
* **QA chunking**: for Q\&A documents, chunks by question.

#### **Direct chunking**

When the original content has no clear Q&A structure, or you want to create chunks quickly, use **direct chunking**. The system splits the text automatically according to your settings.

<table><thead><tr><th width="180">Method</th><th>Description</th></tr></thead><tbody><tr><td>Automatic</td><td>By default the system chunks automatically based on the length and language structure of the input, which suits getting started quickly without custom rules. When no chunking method is specified, the system chunks initially on line breaks, periods and other common marks.</td></tr><tr><td>Token chunking</td><td>Splits the text by the token length you set. We recommend keeping chunks between 100 and 1000 tokens, so the meaning is not broken up and the context is not cut off.</td></tr><tr><td>Custom rules</td><td>Gives finer control: besides chunk length (100–1000 recommended) and overlap (100 tokens, for example), you can also set separators to control chunking.</td></tr><tr><td>Regex chunking</td><td>Splits the text on specific characters (such as <code>\\n</code>, <code>。</code>, <code>,</code> or <code>;</code>). Several marks can be combined, which suits general natural language processing.</td></tr></tbody></table>

<table><thead><tr><th width="180">Option</th><th width="200">Applies to</th><th>Description</th></tr></thead><tbody><tr><td>Ideal chunk length</td><td>Token chunking, custom rules</td><td>The target length of each chunk, in tokens. A smaller value gives finer chunks but may weaken the connection between them; a larger value should be paired with overlap to keep the context consistent.</td></tr><tr><td>Overlap</td><td>Token chunking, custom rules</td><td>How many tokens each chunk repeats from the previous one (100, for example), which improves continuity. A value between 1 and the ideal length minus 1 is recommended. Suits multi-turn conversations, technical documents and other content that depends heavily on context.</td></tr><tr><td>Custom separators</td><td>Custom rules</td><td>The marks that identify a chunk boundary, separated by semicolons. For example, setting <code>;; ;'';</code> creates a chunk wherever <code>;</code>, <code>(space)</code> or <code>''</code> appears in the text.</td></tr><tr><td>Rule</td><td>Regex chunking</td><td>Your own chunking regex. Click one of the presets below to edit it: <code>.+\\n?</code> (chunk on line breaks), <code>[^。]+。?</code> (chunk on the Chinese period).</td></tr><tr><td>Remove trailing line break</td><td>Regex chunking</td><td>Whether to remove the trailing blank line <code>\\n$</code> automatically.</td></tr></tbody></table>

> Tip: token chunking plus overlap keeps meaning and context intact effectively, so sentences are not cut in half and information is not lost.

#### **QA chunking**

For Q&A documents such as FAQs, support records or interview transcripts, QA chunking improves structure recognition and semantic clarity. The system provides the following parameters for identifying and splitting question and answer blocks.

<table><thead><tr><th width="200">Option</th><th>Description</th></tr></thead><tbody><tr><td>Question prefix</td><td>The string that marks the start of a question (such as <code>Q:</code> or <code>Question:</code>). The system treats it as the start of a new question block.</td></tr><tr><td>Answer prefix</td><td>The string that marks the start of an answer (such as <code>A:</code> or <code>Answer:</code>), used to mark the answer to a question.</td></tr><tr><td>Remove prefix</td><td>When enabled, removes the marker strings (such as <code>Q:</code> and <code>A:</code>) from the start of question and answer blocks automatically.</td></tr><tr><td>Prefix expression</td><td>Supports regular expressions for identifying question and answer prefixes, which suits inconsistent formats or large-scale conversions. For example, <code>^Q[0-9]*:</code> matches numbered questions.</td></tr><tr><td>Remove trailing line break</td><td>When enabled, removes extra line breaks at the end of each QA block automatically.</td></tr></tbody></table>

## **Viewing and editing a dataset**

Click a file name in the file list to open the _chunks_ view, where you can read the indexed content and edit it as needed.

<figure><img src="../.gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="80">Item</th><th width="180">Option</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Back</td><td>Returns to the dataset home page</td></tr><tr><td>2</td><td>Edit</td><td>Shows the <em>Edit</em> and <em>Delete</em> actions for a chunk</td></tr><tr><td>3</td><td>Search field</td><td>Search for chunks by text</td></tr><tr><td>4</td><td>Add / Import</td><td>Add a chunk manually</td></tr><tr><td>5</td><td>Reference file</td><td>Shows all files associated with the chunk, including the original file it was chunked from and files used as reference material</td></tr></tbody></table>

## **Editing chunk content**

You can refine chunk content to improve the accuracy of the data an LLM cites in its responses — for example by adding other possible phrasings of a question to a Q\&A chunk.

<figure><img src="../.gitbook/assets/image (39).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (40).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>

1. Click the chunk's **Edit** button and select _Edit_.
2. Click the **Edit** button in the upper right of the dialog to open the editable fields.
3. Click the "+" button to the right of the _Question_ heading to add a question.
4. Enter the question and click the "✔️" button in the upper right to save.

## **Adding a reference file**

When AI Studio cites dataset content in a response, it can include related files as sources — for example specific pages or images from a PDF or PPT.

<figure><img src="../.gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (45).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (46).png" alt=""><figcaption></figcaption></figure>

1. Click **Reference File** in the upper right.
2. Click the "+" button to open the system dialog.
3. Select the files to upload and click _Confirm_.
4. The reference file is now attached.

## **Testing**

Once a dataset is created, use Testing to ask questions, see which chunks were cited in the response, and score the search results while adjusting the retrieval parameters, so you can refine the data and improve citation accuracy.

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (49).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (51).png" alt=""><figcaption></figcaption></figure>

1. Click **Testing** in the **Knowledge Base**.
2. Click the gear button to open the retrieval parameter settings.
3. Select the model you want in the **Rerank model** menu.
4. Click **Confirm** to save the parameters.
5. Enter the content or question in **Query text** and click _Query_ to submit it.
6. The results are listed under **Recall results**, ordered by recall score.
7. Click any _recall result_ to see its full content, and click the **Index** tab to see the index the system used to retrieve that chunk.

> Note: Retrieval parameters set on the Testing tab are kept temporarily. If you leave the page (by switching to the list page, for example) and open the Testing tab of the same knowledge again, your last settings are filled in. These parameters are for testing only and do not affect an Agent's settings.

### Recall and reranking

<figure><img src="../.gitbook/assets/image (52).png" alt=""><figcaption></figcaption></figure>

Knowledge retrieval runs in two stages — retrieval first, then reranking — to balance completeness and accuracy.

* **Retrieval**: in the first stage, the system uses semantic similarity to find a batch of content in the knowledge base that may be relevant to the question. This stage focuses on coverage, so that nothing potentially useful is missed.
* **Rerank**: in the second stage, an LLM evaluates how relevant each piece of that content is to the question, reorders it, and keeps only the most relevant content as the basis for the response.

| Stage     | Purpose               | Description                                                                          |
| --------- | --------------------- | ------------------------------------------------------------------------------------ |
| Retrieval | Improves completeness | Uses semantic similarity (vector search) to find potentially relevant content broadly |
| Rerank    | Improves accuracy     | An LLM evaluates how relevant each piece of content is, reorders it and keeps the most relevant chunks |

> Note: retrieval focuses on completeness, reranking on the accuracy of the results. They complement each other, and without reranking the accuracy of the results may drop.
