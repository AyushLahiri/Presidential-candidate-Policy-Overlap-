# Analysis of Presidential Primary Debate Speech Patterns

## Summary

This project examines whether presidential candidates in U.S. primary elections present distinct policy alternatives relative to their intra-party competitors. We analyze how candidates from 2000 to 2023 group together based on their debate speeches and whether nominees and winners exhibit unique policy stances and semantic patterns.

## Research Objective

- Assess if candidates present distinct policy alternatives beyond party-oriented ideological leanings.
- Investigate whether uniqueness across specific policy topics contributes to clustering patterns.

## Data

**Source**: The American Presidency Project (APP) (Peters & Woolley, 2016)

**Collection**: 
- Transcripts of presidential primary debates from 2000 to 2023.
- Scraping text files and converted to a document-level tabular format with metadata.

**Corpus**:
- Final 8 Republican/Democratic presidential debates per election cycle.
- Only candidate responses included, resulting in a final dataset of 9259 rows.

## Methodologies

### 1. Topic Modelling with BERT

- **Reason**: Traditional LDA struggles with the semantic context and noise in debate speeches.
- **Process**:
  - Utilize BERT to generate word embeddings based on context.
  - Cluster document-level embeddings to identify prominent topics.
- **Evaluation**: Manual review of representative documents and bag of words.

### 2. Word and Document Embeddings

- **Tool**: Doc2Vec, an extension of Word2Vec.
- **Process**:
  - Create word vectors capturing linguistic context using the CBOW variant of Word2Vec.
  - Generate document embeddings to encapsulate each document's essence.

### 3. Agglomerative Hierarchical Clustering

- **Process**:
  - Concatenate all documents for each candidate per election cycle into a single large document.
  - Use agglomerative hierarchical clustering with Ward's linkage for cohesive groupings.
  - Determine the optimal number of clusters using the dendrogram cutting method.
- **Evaluation**: Cophenetic correlation coefficient to measure clustering quality.

### 4. Cosine Similarity

- **Tool**: Cosine similarity to measure the similarity between word embeddings.
- **Process**:
  - Compare word embedding vectors between speakers for identified topics.
  - Cosine similarity score ranges from 1 (identical) to -1 (perfectly inverse).

## Conclusion

Through exploratory and inferential analysis using text processing, topic modeling, and clustering, this project aims to provide insights into the policy distinctiveness of presidential candidates in primary debates.
