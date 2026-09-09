---
order: 4
title: "RAG Chatbot — Retrieval-Augmented Document QA"
subtitle: "Question answering over uploaded PDFs with a locally served open-weights language model."
period: "2025"
org: "AI VIETNAM AIO2025 · team MIX002"
summary: "End-to-end retrieval-augmented generation system — semantic chunking, vector retrieval, and a 4-bit quantized 7B model, served as a Streamlit application."
tech: ["LangChain", "Chroma", "Hugging Face Transformers", "Quantized inference", "Streamlit"]
repo: "https://github.com/aio25-mix002/rag-chatbot-streamlit"
---

A language model asked about a document it never saw during training has two
options: refuse, or invent. Retrieval-augmented generation removes that choice.
The retrieval step places the actual source passages into the prompt, so the
model's task narrows from recall to reading comprehension — more reliable, and
auditable, because every answer can be traced back to the passages that produced
it.

The trade-off is that answer quality becomes a function of retrieval quality. A
retriever that returns the wrong passages will lead a perfectly capable model to
answer the wrong question with full confidence. Most of the design decisions
below follow from taking that seriously.

## What it does

- Loads one or more uploaded PDFs and splits them with a **semantic chunker**,
  cutting at points where embedding similarity actually drops rather than at a
  fixed character count that can sever a sentence or an argument.
- Embeds the chunks with a bi-encoder matched to the corpus language and indexes
  them in a **Chroma** vector store, held locally with no external service.
- Serves **Vicuna-7B under 4-bit NF4 quantization**, which fits a 7B model onto
  consumer or Colab-class GPUs; a full-precision path is retained for larger cards.
- Composes retrieval, prompt construction, generation, and parsing as a
  **LangChain Expression Language pipeline**, so each stage can be replaced
  independently, with prompt templates versioned as files rather than embedded in
  code.
- Carries a window of recent conversation into each prompt, so follow-up questions
  resolve against earlier turns.

## What it does not do

The system reports no retrieval evaluation — there is no held-out question set
measuring recall or answer faithfulness, so retrieval quality is assessed by
inspection alone. Uploading a new document resets the vector store rather than
extending it, and answers do not yet cite the page they came from, although the
chunk metadata to support that is retained. These are the limitations that make
an evaluation harness, rather than a further chatbot, the natural next piece of
work.

## Attribution

A team project built for module M01, project P0102 of the AI VIETNAM AIO2025
program, with two collaborators.
