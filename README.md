# LangChain Documentation Deep Agent

A Python project that builds a deep retrieval-augmented generation (RAG) agent for LangChain documentation. It fetches selected LangChain docs, splits them into chunks, stores them in an in-memory vector database, and uses a deep agent workflow to answer questions grounded in the retrieved documentation.

## Project Overview

This project demonstrates:

- Loading LangChain documentation pages from the official docs site
- Chunking documentation into searchable text segments
- Indexing content with embeddings using `OpenAIEmbeddings`
- Searching relevant documentation through a custom tool
- Delegating fact extraction to subagents for each retrieved chunk
- Synthesizing final answers based on documentation evidence

## Main Features

- Document retrieval from LangChain docs
- Vectorized search over relevant pages
- Chunk analysis with subagents
- Agent-driven question answering
- Retrieval outputs saved under `/retrieved/` for analysis

## Project Structure

- `main.py` — main project logic and agent setup
- `README.md` — project documentation

## Requirements

Install the required Python packages:

```bash
pip install requests langchain langchain-core langchain-openai langchain-text-splitters deepagents
```

You may also need the following environment variables configured in your shell or `.env` file:

```bash
export OPENAI_API_KEY="your_openai_api_key"
export ANTHROPIC_API_KEY="your_anthropic_api_key"
```

## Run the Project

From this folder:

```bash
python main.py
```

The script currently runs a sample query:

> How do I stream intermediate tool results from a subagent?

## How It Works

1. The script loads a curated set of LangChain documentation pages.
2. The content is split into manageable chunks.
3. Embeddings are created and stored in an in-memory vector store.
4. A custom tool (`search_documentation`) searches the local index for the most relevant chunks.
5. The agent delegates chunk analysis to subagents and merges the findings into a final AI response.

## Notes

- The project relies on external APIs and valid API keys.
- It fetches documentation pages from the public LangChain docs website.
- Retrieval results are stored in the `retrieved` directory at runtime.

## License

This project is intended for educational and experimentation purposes.
