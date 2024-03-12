+++
title = 'RAG Chronicles 2'
date = 2024-03-05T08:50:13-05:00
draft = true
+++


## RAG Chronicles 2

This is article 2 about building a RAG application.
## RAG Overview

RAG logically can be divided into

- Ingestion Service
- Inference Service
- Vector Database
- User or API server

### The RAG Pipeline

![img_6.png](resources/img_6.png)


### Some RAG Concepts



* Small to Big Retrieval 
#### Small to Big Retrieval 

Description:
* Chunk your documents into small chunks (ie 'sentences.')
  * Small chunks lead to vectors with ...
* Find the closest vector to your query
* Retrieve the selected node and surrounding context 
When you look up the sentences
  See https://docs.llamaindex.ai/en/latest/examples/node_postprocessor/MetadataReplacementDemo.html
* 



![img_5.png](resources/img_5.png)


### RAG Example 1

### RAG Example 2

### RAG Example 3

### RAG Example 4

### RAG Example 5

### RAG Example 6 

SentenceWindowNodeParser


### RAG Example 7


### RAG FAQ

Some Questions & Answers about RAG