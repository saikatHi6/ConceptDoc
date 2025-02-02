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
