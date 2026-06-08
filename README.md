# RAG From Scratch

## Origin

After watching 3Blue1Brown's introduction to LLMs, I wanted to build something of my own. I kept getting confused about how to take tablets and dosages, so I thought — why not build a model that can answer these questions efficiently? That's when I stumbled onto RAG.

## What I Built

A complete Retrieval Augmented Generation (RAG) pipeline built from scratch — no LangChain, no shortcuts. Just the raw components so I could understand exactly what's happening under the hood.

## What I Learned

- **Word embeddings** — how text is converted into vectors where position carries semantic meaning
- **Cosine similarity** — how to measure semantic similarity between two pieces of text
- **Vector databases** — why we use ChromaDB instead of traditional SQL search
- **RAG pipeline** — how retrieval and generation work together to give grounded answers
- **Hallucination** — why LLMs make things up, and how RAG fixes it by grounding answers in context

## How It Works

```
User question
↓
Convert question to embedding (sentence-transformers)
↓
Search ChromaDB for semantically similar documents
↓
Send retrieved documents + question to LLM as context
↓
LLM generates a grounded answer
```

## Tech Stack

- **sentence-transformers** — converts text to embeddings locally
- **ChromaDB** — local vector database for storing and searching embeddings
- **Ollama + llama3.2** — local LLM for answer generation (free, no API key needed)
- **uv** — Python package manager

## Why RAG?

Traditional keyword search is brittle — searching "paracetamol dosage" won't find documents about "acetaminophen" or "Tylenol" even though they're the same thing. RAG uses semantic search, so meaning is matched, not just words. This is especially important for medical data where the same drug can have many names.

## What's Next

- Rebuild this pipeline using LangChain to see how it simplifies things
- Add a vision model to recognise medicine tablets from images
- Build a full multi-modal system: scan a tablet → identify it → answer questions about dosage and usage
