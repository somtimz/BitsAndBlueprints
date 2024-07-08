+++
title = 'RAG Notes'
date = 2024-04-03T08:50:13-05:00
draft = true
+++

## What Problems Does LlamaIndex Solve?

- A way to ingest data into a vector store
- A way to create queries  

## Notes about LlamaIndex

Note that Behind the Scenes:

- the input documents are loaded
- the input documents are chunked, embeddings created and stored in a vector db
  - The vector db is created 
- a query engine combines:
  - Retriever
    - turns the question into an embedding that can be sued to call the vector db
    - Calls the vector db to get the best matches
  - Performs postprocessing ion retreived nodes
- Synthesizes the query to a LLM
  - Creates a context
    - Combines the question, context and prompt
    - Submits the prompt to the LLM

- Things you can cusotmize:
  - How the documents are processed (split)
  - Embedding used (model, vector size, )
  - Upsert to VDB
  - Query parameters
  - Prompt
  - LLM Used


```python

const documents = await new SimpleDirectoryReader()
    .loadData({directoryPath: "./data"})

const index = await VectorStoreIndex.fromDocuments(documents)
const queryEngine = index.asQueryEngine()
const response = await queryEngine.query({
    query: "What did the author do in college?"
})
console.log(response.toString())

# In order to customize do this:

let customServiceContext = new llamaIndex.serviceContextFromDefaults({
    llm: new llamaIndex.OpenAI(),
    embedModel: new llamaIndex.OpenAIEmbedding()
})

let customQaPrompt = function({context = "", query = ""}) {
    return `Context information is below.
        ---------------------
        ${context}
        ---------------------
 
        Given the context information, answer the query.
        Include a random fact about whales in your answer.\
        The whale fact can come from your training data.
 
        Query: ${query}
        Answer:`
}

let customResponseBuilder = new llamaIndex.SimpleResponseBuilder(
    customServiceContext,
    customQaPrompt
)

let customSynthesizer = new llamaIndex.ResponseSynthesizer({
    responseBuilder: customResponseBuilder,
    serviceContext: customServiceContext
})

let customRetriever = new llamaIndex.VectorIndexRetriever({
    index
})

let customQueryEngine = new llamaIndex.RetrieverQueryEngine(
    customRetriever,
    customSynthesizer
)

let response2 = await customQueryEngine.query({
    query: "What does the author think of college?"
})

console.log(response2.toString())

```


## Routing Queries

The ability of the RAG system to understand how to answer a query is a powerful feature. 

Example:
- Route by user
- Route by domain
- Route by security and access privileges



Whta Problems Does a RAG system have to Solve?

- Get the Data 
- Curate the Data
  - Eliminate bad data (duplicates, outdated, errors, )
- Index the Data

- Handle the query
- Create the Retriever
- Create the Synthesizer
- Submit the Request

