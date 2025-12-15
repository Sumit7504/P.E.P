## What is RAG?

RAG = Retrieval-Augmented Generation.
It means the AI first retrieves real data from documents, PDFs, websites, DB, etc.,  
and then generates an answer based only on that data.

This reduces hallucinations
Makes AI reliable
Helps in building real AI apps (chatbots, search, assistants)

## Why RAG is Important?

1. Prevents hallucination

AI answers only from real documents.

2. Useful for real projects

HR Chatbot  
Product Q/A  
Customer Support  
PDF Chat  
Codebase Search  
Learning Assistants

3. AI Web Full Stack Developer MUST know RAG

Because companies want developers who can build AI-powered apps connected to data.

## How RAG Works

```
User Query
     ↓
Retriever (Search in your documents)
     ↓
Embeddings (Convert text → vectors)
     ↓
Top-k Relevant Documents
     ↓
LLM Generates Answer Using Retrieved Context

```

## Exercise — Create a RAG Prompt Template

Use only the context below to answer.
If not in context, say: "Not in document".

```
You are a retrieval-based assistant.

Rules:
- Answer ONLY using the context.
- If the answer is not found, say “Not in context”.
- Do not hallucinate or guess.

Context:
{{document_chunks}}

User Question:
{{query}}
```

# Exercise — Create a Mini RAG Dataset

data/
│── india-gdp.txt
│── ai-history.txt
│── react-basics.txt

```ai-history.txt
Deep learning became popular after 2012 due to AlexNet.
Neural networks were first proposed in 1943 by McCulloch and Pitts.
Transformers were introduced by Google in 2017.
```

```react-basics.txt
React is a JavaScript library for building UI.
It is component-based and uses Virtual DOM for fast rendering.
Developed by Facebook in 2013.
```

## Exercise — Write Chunking Strategy

Write how you would chunk long documents (simple, not technical).

```
“RAG is a method where AI retrieves information from documents before generating an answer. Instead of guessing, it uses real stored data. This makes the output more accurate, reduces hallucination, and is useful in real-world apps like chatbots, PDF search, or customer support bots.”
```
