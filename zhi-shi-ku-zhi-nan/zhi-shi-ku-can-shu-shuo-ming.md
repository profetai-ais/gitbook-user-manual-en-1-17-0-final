# Knowledge Base Parameters

## Where the parameters are

Knowledge base parameters can be adjusted in the three places below. When an Agent answers a question, it first searches the selected knowledge sources for relevant content, then passes the matching data to the model for reference. These settings **only affect how knowledge data is searched and cited**; they **do not change the original documents in the knowledge base**.

### **Chat Agent**

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

1. Open the Agent settings and click the gear icon on **Knowledge**.
2. Select the **Parameters** tab.

### **Workflow Agent**

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

1. Open the workflow editor.
2. Click the LLM node.
3. Click the **Knowledge** gear icon.
4. Switch to the **Parameters** tab; the screen shows the current retrieval parameters.

> Note: The **Knowledge** toggle has to be on to use this.

### **The Testing tab in the Knowledge Base**

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

1. Open the Knowledge Base's Testing tab and click the gear icon shown in the image.
2. The screen shows the current retrieval parameters. To change other settings, click the gear icon again.

> Note: Parameters set on the Knowledge Base Testing tab are for testing only and **do not affect any Agent**. To change an Agent's parameters, configure them in that Agent.

## Parameters

### Search strategy

<figure><img src="../.gitbook/assets/image (93).png" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="161">Parameter</th><th>What it does</th></tr></thead><tbody><tr><td>Max references</td><td>The maximum number of references a search can provide. A reference is usually a chunk of a document, not a whole document. A higher value covers more ground but may bring in more irrelevant information; a lower value keeps results focused.</td></tr><tr><td>Minimum relevance threshold</td><td>The minimum relevance score for initial search results. Content scoring below this value is not used. A higher threshold reduces irrelevant results but may miss usable data; a lower one widens the search but may give more scattered results.</td></tr><tr><td>Retrieval preference</td><td>Balances semantic search against keyword search. Weighted toward semantic search, the system looks for content close to the overall meaning of the question; weighted toward keyword search, it prioritizes matching the same or similar words.</td></tr></tbody></table>

#### **The difference between semantic and keyword search**

* Semantic search suits natural sentences, synonyms and different phrasings. If a user asks "how do I reset my password", it may also find content titled "what to do if you forget your password".
* Keyword search suits product names, specialized terms, IDs, error codes and anything that needs an exact text match.
* If both cases are likely, set the retrieval preference in the middle to use semantic and keyword search together.

### Advanced settings

<figure><img src="../.gitbook/assets/image (94).png" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="211">Parameter</th><th>What it does</th></tr></thead><tbody><tr><td>Rerank results</td><td>When enabled, the system uses the model you specify to judge again how relevant the initial results are to the question, and reorders them. This helps put the most relevant content first, but may add some processing time.</td></tr><tr><td>Rerank model</td><td>The model that reranks the search results. It mainly judges how relevant the question and the knowledge content are, and is not necessarily the same model the Agent uses to produce its final answer. An administrator can set the system's default rerank model under <strong>System Setting → Configuration → Default model</strong>.</td></tr><tr><td>Rerank score threshold</td><td>The minimum relevance score after reranking. Content scoring below this value is excluded. A higher value keeps more precise results, but the criteria can be so strict that nothing is found.</td></tr><tr><td>Query expansion</td><td><p>Query expansion is a pre-processing step before retrieval. When enabled, a language model adds synonyms, related terms and multilingual terminology to the user's question, rewriting it into several semantically similar phrasings that are all used for retrieval, which improves the chance of finding relevant content.</p><ul><li><strong>When to use it</strong>: a user's question may be short, or may not use the same wording as the knowledge base. Retrieving with the original question alone can miss content that means the same thing in different words. Query expansion covers those phrasings and reduces such misses.</li><li><strong>Example</strong>: when a user enters "remote work", the model may also retrieve with similar phrasings such as "working from home" or "telecommuting".</li></ul></td></tr><tr><td>Dataset filtering</td><td>When several knowledge sources are selected, the system first works out which datasets are more relevant to the question and searches those, which reduces hits on other topics. With a single dataset, this setting has little effect.</td></tr><tr><td>Run this instruction when nothing is found</td><td>With dataset filtering enabled, this setting defines how the system responds when the results do not meet the relevance threshold, or when nothing usable remains after reranking.</td></tr></tbody></table>

#### The difference between the two relevance thresholds

The two scores are used at different stages:

1. The system searches the knowledge base and uses the **minimum relevance score** to exclude clearly irrelevant content.
2. If **rerank results** is enabled, the system checks and reorders what remains.
3. The system then filters a second time with the **rerank minimum score**.
4. If nothing usable is left, it runs the **what to do when nothing is found** setting.

## How knowledge base search parameters work

The search runs in two stages:

**Stage one: hybrid search**

Hybrid search finds references relevant to the question in the knowledge base and passes the matching results to the next stage.

* Max references: how many references can be retrieved at most.
* Minimum relevance threshold: the minimum relevance score for a reference. Only data at or above this threshold is kept and passed on.
* Search preference: adjusts the search method, for example toward semantic or keyword search.

For example:

* Max references set to 10: at most 10 references are retrieved.
* Minimum relevance threshold set to 0.2: only data scoring 0.2 or above is kept.

**Stage two: LLM reranking**

References that pass stage one are re-evaluated for relevance and reordered by the LLM you specify.

* Enable reranking: when selected, the system reranks the results with an LLM.
* Rerank model: the LLM that evaluates and reorders them.
* Rerank score threshold: the minimum passing score after reranking. Only references at or above it are kept for the answer.

For example:

* Rerank score threshold set to 0.5: only data scoring 0.5 or above passes stage two.

## Tuning tips

* If irrelevant content keeps coming up, raise the minimum score, reduce the maximum number of references, or enable reranking.
* If the knowledge base clearly has the data but it is not found, lower the minimum score, increase the maximum number of references, or enable query expansion.
* If you mostly search for error codes, IDs or specialized terms, weight the search further toward text matching.
* If you use several datasets on different topics at once, enable dataset filtering.
* After adjusting, test common questions in the **Debug Preview** to confirm the results are what you expect.
