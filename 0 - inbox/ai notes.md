---
status: newBorn
related-links:
created: 1970-01-01T05:30
updated: 2025-12-28T17:16
---
---

So when we search calories in apple and employees in Apple, how does Google knows that which apple is a fruit and which apple is the company? So the answer is semantic search. Semantic search means it doesn't just map the word with a meaning, it tries to understand the concept and the context behind it. So that's how semantic search, what semantic search is, and how semantic search works is through embedding and vector databases. So right now we are going to try and learn that.


So embedding is basically nothing but converting a word or a sentence, into numerical values. So let's see.
![[celluloid-shot0002.jpg]]

![[celluloid-shot0003.jpg]]

So here, as we can see, that with embeddings, we can convert a word or any sentence into a vector. And as we go further down the line, we can see that when we have vectors for any application, then there can be thousands or millions of vectors. And so for storing those vectors, first thing that comes to our mind is a database. And that is any database, that is SQL database or non-SQL database. But these are not the ones that we will go with.

![[celluloid-shot0004.jpg]]

some techniques that are used to create embeddings. 


- When we store a large number of vectors in a database, performing a linear search for every query becomes computationally expensive. If we compare the query vector with every stored vector to compute similarity scores, it would require searching through millions or even billions of vectors, which is not feasible. To solve this, vector databases use hashing techniques such as **Locality-Sensitive Hashing (LSH)**. In LSH, vectors are hashed using special hash functions that preserve similarity, meaning similar vectors are likely to fall into the same bucket. These hash functions are typically based on random projections (or hyperplanes) that split the vector space so that vectors with similar directions end up in the same bucket. When a search query arrives, it is hashed using the same function and mapped to one or a few relevant buckets. Instead of searching the entire database, we now only search within these buckets. Inside the selected bucket, we compute exact similarity—commonly using **cosine similarity**, which measures how closely aligned two vectors are—to rank the results. This significantly reduces computational cost while still returning highly relevant matches, which is the core power of vector databases.
- So the advantages of using vector database is that it helps us search things fast and it helps it stores the data in an optimized way.
- for more techniques read this article: [What is a Vector Database & How Does it Work? Use Cases + Examples \| Pinecone](https://www.pinecone.io/learn/vector-database/) 


## RAG and Langchain

![[celluloid-shot0005.jpg]]

- RAG stands for **Retrieval-Augmented Generation**. The main purpose of RAG is to allow a Large Language Model (LLM) to access **external documents or data sources** that were **not part of its training data** and use that retrieved information to generate more accurate and up-to-date answers. In a RAG system, when a user asks a question, the system first retrieves relevant documents from an external knowledge base (often using a vector database), and then provides those documents as context to the LLM. The LLM uses this retrieved context to generate its final response. This helps reduce hallucinations and allows the model to answer questions about private, domain-specific, or recent data.
- LangChain, on the other hand, is a **Python framework** that helps developers build applications powered by LLMs. It acts as a glue layer that connects different components such as language models, vector databases, retrievers, prompts, and external tools. LangChain makes it easy to integrate and switch between different LLMs in a plug-and-play manner. For example, you can start with an OpenAI model and later switch to an open-source LLaMA-based model with minimal code changes. Because of this abstraction, LangChain helps make applications more modular, flexible, and model-agnostic, which is especially useful when building RAG-based systems.
- In a RAG system, the core idea is to retrieve relevant external documents and provide them as context to the LLM before generation. LangChain acts as the orchestration framework that connects all the components required for this pipeline. Using LangChain, documents are first loaded and converted into embeddings, which are stored in a vector database. When a user query comes in, LangChain uses a retriever to fetch the most relevant documents based on vector similarity. These retrieved documents are then injected into a prompt and passed to the LLM for response generation. Because LangChain abstracts the LLM and retriever interfaces, the same RAG pipeline can work with different models (such as OpenAI or open-source LLaMA models) and different vector databases with minimal changes. In this way, LangChain provides the structure and flexibility, while RAG provides the methodology for grounding LLM responses in external knowledge.


![[Pasted image 20251228145012.png]]

- As we know, large language models (LLMs) are created by companies such as OpenAI. The ChatGPT website that we use is itself a software application, and it does not contain the model directly. Instead, it communicates with models like GPT-3.5, GPT-4, and newer versions through an API. Between the application and the model, there is an API layer. When we directly use an LLM through an API in our own applications, a major issue is cost, because each API call is charged, and as usage scales, the cost increases significantly. It is not that LLM providers cannot solve this problem, but rather that their goal is to provide the core LLM capabilities, while allowing others to build frameworks and tooling on top of them. This is where **LangChain** comes in. LangChain allows us to connect our application to different LLMs and also to external data sources. It provides a plug-and-play architecture that makes it easy to switch between models without rewriting the entire application logic. As a result, we can focus on building our application without worrying that changing the underlying model later will require major code changes.