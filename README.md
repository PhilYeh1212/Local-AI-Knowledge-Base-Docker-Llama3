# 🔒 Private ChatGPT Stack — Self-Hosted RAG with Llama 3 & Docker (100% Offline)

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)
[![Docker](https://img.shields.io/badge/Docker-Compose-2496ED.svg)](https://www.docker.com/)
[![Ollama](https://img.shields.io/badge/Ollama-Llama%203-50e69a.svg)](https://ollama.com/)
[![License](https://img.shields.io/badge/License-MIT--like-lightgrey.svg)](#-license)

> **Build a private ChatGPT replacement that runs on your own hardware.**
> Index your confidential documents (PDF / TXT / MD / DOCX), chat with
> them, get answers with citations — for the price of two months of
> ChatGPT Plus, **forever**, with zero data leaving your machine.

Private ChatGPT Stack screenshot
<img width="1280" height="720" alt="rag_cover" src="https://github.com/user-attachments/assets/a4c98506-a9c4-48cf-8460-e23f994538e7" />


# Private ChatGPT Stack

> A self-hosted RAG (Retrieval-Augmented Generation) stack with Llama 3, Docker, and one-click start scripts. Chat with your engineering docs, manuals, and codebases without sending anything to OpenAI.

**This is a commercial tool, sold on Gumroad.** Source code is included in your purchase.

---

## What it does

- **100% offline** after initial model download — no API keys, no token costs, no privacy leaks
- **Llama 3** local LLM via Ollama (8B or 70B depending on your GPU)
- **RAG over your documents** — point it at a folder, get a chatbot trained on your files
- **Supports** PDF, DOCX, TXT, Markdown, and source code (Python, JS, C, etc.)
- **One-click start** — `start.sh` (macOS / Linux) and `start.bat` (Windows)
- **Docker-based** — every component containerized, no Python venv conflicts
- **Web UI** for chat (no need to memorize CLI flags)
- **Vector search** with ChromaDB for semantic retrieval
- **No telemetry** — your queries never leave your machine

## Why this exists

I work with industrial controls documentation that contains sensitive customer data. I can't paste it into ChatGPT. The few existing "private LLM" projects assume you have a Kubernetes cluster and 4 hours to spare on configuration.

This stack is what I built so I could chat with my own engineering manuals on a laptop. Five minutes from download to first query.

## Who this is for

| Audience | Why it fits |
|---|---|
| Engineers with NDA documents | Query technical manuals without leaking IP |
| Companies on data residency policies | Keep all queries on-premise |
| Researchers | Chat with paper PDFs without cloud dependency |
| Indie devs / consultants | Replace ChatGPT subscription for project docs |
| Privacy-conscious users | No data goes to any third-party API |

## What's in the stack

- **Ollama** — local LLM runtime
- **Llama 3** — pick 8B for laptops, 70B for workstations with 48GB+ VRAM
- **LangChain** — RAG orchestration
- **ChromaDB** — vector store for embeddings
- **Streamlit** — web chat UI
- **Docker Compose** — single-file orchestration

## Hardware requirements

| Tier | RAM | GPU | Model | Use case |
|---|---|---|---|---|
| Minimum | 16 GB | None (CPU only) | Llama 3 8B Q4 | Small docs (<100 pages) |
| Recommended | 32 GB | RTX 3060+ (8 GB VRAM) | Llama 3 8B FP16 | Medium docs (<1000 pages) |
| Power user | 64 GB | RTX 4090 / A6000 | Llama 3 70B Q4 | Large knowledge bases |

## Get it

→ **[Private ChatGPT Stack on Gumroad — $59](https://philyeh.gumroad.com/l/private-chatgpt-stack)**

## What's in the purchase

- `start.sh` / `start.bat` — One-click bootstrap
- `docker-compose.yml` — Full stack orchestration
- `rag_pipeline.py` — Document ingestion + retrieval logic
- `requirements.txt` — Pinned dependencies
- `README.md` — Setup guide for Windows / macOS / Linux
- Commercial use license per Gumroad EULA

## License

Commercial use license per Gumroad EULA. You may use this software at the company that purchased it for any commercial purpose. Redistribution, resale, or open-sourcing the code is not permitted.

Note: Llama 3 itself is governed by Meta's Llama 3 License, which you must accept separately when downloading the model.

## Support

- Reply to your Gumroad purchase email
- Setup issues / model questions via [GitHub Issues](https://github.com/PhilYeh1212/Local-AI-Knowledge-Base-Docker-Llama3/issues)

---

I write about industrial Python and protocol internals at **[dev.to/philyeh](https://dev.to/philyeh)**, and post Chinese versions on [iThelp](https://ithelp.ithome.com.tw/users/20171204).

— Phil Yeh · Senior Automation Engineer · Industrial Python · Developer Tools

