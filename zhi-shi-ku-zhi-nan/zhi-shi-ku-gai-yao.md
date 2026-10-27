# Knowledge Base Overview

## Introduction

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

The Knowledge Base in AI Studio gives application developers an easy interface for managing personal or team knowledge and integrating it seamlessly into AI Agents. You can upload internal documents, FAQs and standard operating procedures, and have them processed into structured data that large language models (LLMs) can query.

Unlike the static pre-trained datasets built into an AI model, the content of a knowledge base can be updated at any time, so the LLM always has access to the latest information and does not answer from outdated or missing data.

When an LLM receives a user query, the system uses hybrid search to find the most relevant content in the knowledge base. Hybrid search combines the following signals and ranks the results together:

* Full-text search: uses the database's full-text index (Postgres) to find passages that closely match the query terms.
* Vector search: uses semantic similarity to find content that matches the concept of the question, even without the same words.
* Chunk Summary Index: uses chunk summaries and key-point indexes to locate the important passages in long documents, which sharpens recall.

The system returns the most relevant chunks as context for the LLM, so its answers are more accurate and their sources can be traced. This way the LLM does not rely on its pre-trained knowledge alone, but also draws on the latest internal documents and database content, which reduces answers skewed by outdated or missing data.

## **Key advantages**

* **Data stays internal**: important knowledge documents stay inside the company environment and never leave the internal network.
* **Always current**: a knowledge base can be updated at any time, so the model has the latest information.
* **Accuracy**: by retrieving relevant documents, the LLM answers from actual information, which reduces the risk of hallucination.
* **Flexibility**: developers can customize the content of a knowledge base and define the scope of knowledge they need.

All you need is text content, for example:

* Long-form text (TXT, Markdown, DOCX, HTML, JSONL, even PDF)
* Structured data (CSV, Excel and so on)

Upload the files to the **Knowledge Base** and the data processing happens automatically.

## **Use case**

If you want to build an AI customer-service Agent from your existing knowledge base and product documentation, upload the relevant files to the AI Studio knowledge base and then create the Agent.

Traditionally, going from raw text to a complete AI customer-service chatbot could take weeks, and was hard to maintain and improve. In AI Studio the whole process takes three minutes, and you can start collecting user feedback right away.

## Knowledge and datasets

In AI Studio, a knowledge base is made up of **datasets**, and each **dataset** can contain many chunks. You can integrate a whole knowledge base into an application as retrieval context, from uploaded files or from content synced from other data sources.
