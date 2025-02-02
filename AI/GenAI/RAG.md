![image](https://github.com/user-attachments/assets/e5168e66-f1e7-4069-b5bd-9d1958acafb8)


Retrieval Algorithms****

- **Similarity Search (Vanilla Search) & Maximum Marginal Relevance(MMR)**
When retrieving documents from a large corpus, most methods use similarity metrics like cosine similarity, Euclidean distance, or dot product to identify documents that are closest to the query or question posed. These metrics effectively pull the most similar documents based on the query, aligning well with the search intent.

However, there arises a challenge when we desire not only similarity but also diversity among the retrieved documents. This need is particularly critical when we want to avoid redundancy and provide a broad perspective on a topic. This is where the concept of Maximum Marginal Relevance (MMR) becomes invaluable.

- **Understanding Maximum Marginal Relevance (MMR)**
MMR is designed to balance between the relevance of the documents to the query and the diversity among the documents selected for retrieval. This approach helps ensure that the returned set of documents is both relevant and varied, providing a comprehensive view of the subject matter.

In practical applications like unsupervised learning for key phrase extraction, MMR can significantly enhance the utility and information quality. For example, consider a scenario where key phrases extracted from product reviews include terms like “Good Product,” “Great Product,” “Nice Product,” “Excellent Product,” “Easy Install,” “Nice UI,” “Lightweight.” Without MMR, the system might overly focus on similar phrases that frequently appear like “Good Product,” “Great Product,” and “Nice Product,” which all describe the same feature of the product and rank highly due to their frequency.

- **Other Methodologies for searching**
  MMR is just one of the many advanced retrieval strategies. Others include Multi Query Retrieval, Long-Context Reorder, Multi-Vector Retriever, Parent Document Retriever, Self-Querying, and Time-weighted Vector Store Retrieval. 

- **Retrieve & Re-Rank Pipeline**
   - Step 1: Initial Retrieval:
      The first stage involves the use of a retrieval system to gather a large set of potential results, typically around 100, that may be relevant to the given search query. This retrieval can be conducted using one of two primary methods:

        - **Lexical Search:** Utilizing traditional search engines like ElasticSearch, this method relies on keyword matching. It scans documents to find occurrences of the words included in the search query. While fast and efficient, lexical search may retrieve documents that match the query terms but miss contextual relevance or semantic similarity.
        - **Dense Retrieval:** Employing a bi-encoder architecture, dense retrieval processes both the query and the documents in the corpus into dense vector representations. These embeddings are then compared (usually via cosine similarity) to identify documents whose contexts are semantically close to that of the query. This method tends to pull more contextually relevant documents compared to lexical search but may still include some less relevant results.
   - Step 2: Re-Ranking with a Cross-Encoder
Once the initial list of potential hits is retrieved, the second stage of the process begins:

        - **Re-Ranking:** A cross-encoder is employed to re-evaluate the relevance of each candidate document to the search query. Unlike the bi-encoder used for dense retrieval, a cross-encoder takes the pair of the query and each individual document as input and outputs a relevance score. This model is more computationally intensive because it performs a deeper analysis of the interaction between the query and document content, considering the nuances of their relationship.
        - **Scoring and Ranking:** The cross-encoder scores each document for its relevance to the query. These scores are then used to sort the documents, resulting in a ranked list where the most relevant documents appear first. This refined list significantly improves the quality of the results that will be presented to the user.



RAG With Different Implementation : 

- https://medium.com/@devmallyakarar/rag-retrieval-augmented-generation-in-depth-with-code-implementation-using-langchain-llamaindex-1f77d1ca2d33
- https://www.linkedin.com/pulse/agentic-rag-using-crewai-langchain-pavan-belagatti-ewwsc/
- https://python.langchain.com/docs/tutorials/rag/
- https://www.youtube.com/watch?v=pdnT3yLk70c
- https://medium.com/@sulaiman.shamasna/rag-iv-agentic-rag-with-llamaindex-b3d80e09eae3


