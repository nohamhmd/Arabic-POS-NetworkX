# Arabic-POS-NetworkX
# Semantic Search with Vector Databases  

This repository demonstrates the implementation of **semantic search** using **vector embeddings** and a **vector database**. It explores how to preprocess, embed, and store textual data for efficient semantic search and retrieval.  

---

## Features  

- **Dataset**: Utilizes the Medium Articles Dataset with 337 articles, including titles and content.  
- **Preprocessing**:  
  - Lowercasing  
  - Removing URLs, HTML tags, special characters, and stopwords  
  - Merging titles and text for enriched context  
- **Text Embeddings**:  
  - Chunking long texts with overlap using `RecursiveCharacterTextSplitter`  
  - Generating embeddings using the `SentenceTransformer` model from HuggingFace  
- **Vector Database**:  
  - Storing and querying embeddings with **ChromaDB**  
  - Efficient semantic search implementation  
- **Keyword Extraction**:  
  - Leveraging `KeyBERT` for contextual keyword and keyphrase extraction  
  - Extracting keywords from retrieved documents to enhance result relevance  

---

## Dataset  

The dataset includes Medium articles with features such as titles and content. Articles exceeding 512 tokens are chunked into smaller segments for embedding, ensuring compatibility with the model.  

---

## Workflow  

1. **Exploratory Data Analysis (EDA)**: Analyze word and character distributions, generate a word cloud, and extract n-grams for thematic understanding.  
2. **Data Preprocessing**: Clean and prepare text data for embedding.  
3. **Vector Embedding**: Use HuggingFace `SentenceTransformer` to embed the data.  
4. **Vector Database**: Store embeddings in ChromaDB for efficient retrieval.  
5. **Semantic Search**: Query the database for articles semantically related to a given input.  
6. **Keyword Extraction**: Extract relevant keywords from retrieved articles using KeyBERT.  

---

## Tools and Libraries  

- **Programming Language**: Python  
- **Libraries/Frameworks**:  
  - Data Manipulation: `pandas`, `numpy`  
  - Text Processing: `nltk`, `re`, `wordcloud`  
  - Machine Learning: `scikit-learn`, `sentence-transformers`, `HuggingFaceEmbeddings`, `KeyBERT`  
  - Vector Database: `chromadb`, `langchain`  
  - Visualization: `matplotlib`, `seaborn`  

---
