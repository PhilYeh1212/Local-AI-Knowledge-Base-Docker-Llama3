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


---

## 📺 Demo Video

[`AI.mp4`](https://github.com/PhilYeh1212/Local-AI-Knowledge-Base-Docker-Llama3/blob/main/) — chat with private engineering docs in real time, fully offline.

---

## 🌟 Why This Tool?

- **🔒 100% Data Privacy** — your data never leaves your machine. No
  OpenAI, no cloud APIs, no risk of leaks. Critical for confidential
  business documents, regulated industries (finance, healthcare, legal),
  and field deployments without reliable internet.
- **💰 Zero Recurring Costs** — buy once, run forever. Compare to ChatGPT
  Plus at $240/year, or commercial RAG SaaS at $50+/user/month.
- **🛠️ Engineer-First Design** — optimized for technical manuals,
  datasheets, and complex documentation that general LLMs struggle with.
- **🐳 Docker Compose Architecture** — three services (Ollama + ChromaDB +
  Streamlit) orchestrated cleanly. No "dependency hell."

---

## 📂 Open Source vs Pro

This repo contains the **Community Edition** — a working RAG stack you
can clone and run, free for personal use and learning.

The **[Private ChatGPT Stack](https://philyeh.gumroad.com)** version on Gumroad
adds the production features that turn this from a demo into a real tool:

| Feature | Community (this repo) | **[Pro Edition ($59)](https://philyeh.gumroad.com)** |
|---|:---:|:---:|
| Three-service Docker architecture | ✅ | ✅ |
| Ollama + Llama 3 + ChromaDB | ✅ | ✅ |
| Streamlit chat UI | ⚠️ Basic | ✅ Production polish |
| **App Dockerfile** (proper build, not bind-mount hack) | ❌ | ✅ |
| **One-click `start.sh` / `start.bat`** (no manual `docker exec`) | ❌ | ✅ |
| **`.env` configuration** (models, ports, chunk size, k) | ❌ | ✅ |
| **Re-Ingest wipes collection first** (no duplicate chunks) | ❌ | ✅ |
| **Source citations** on every answer (file + page) | ❌ | ✅ Pill format |
| **3 prompt personas** (helpful / technical / research) | ❌ | ✅ + custom |
| **Document support** (PDF / TXT / MD / DOCX) | ⚠️ PDF + TXT | ✅ All 4 |
| **Healthchecks** (services wait for each other) | ❌ | ✅ |
| **Stats panel** (file count, chunk count) | ❌ | ✅ |
| **Custom dark UI theme** | ❌ | ✅ |
| **Commercial license** | ❌ | ✅ |
| **Email support** | ❌ | ✅ |

### 👉 [Get Private ChatGPT Stack on Gumroad — $59](https://philyeh.gumroad.com)

---

## 🚀 Quick Start (Community Edition)

### Prerequisites

- Docker Desktop (Windows / Mac) or Docker Engine + Compose v2 (Linux)
- 16 GB RAM minimum (32 GB recommended for larger models)
- NVIDIA GPU strongly recommended (CPU-only works but is ~10× slower)

### Run

```bash
# Clone
git clone https://github.com/PhilYeh1212/Local-AI-Knowledge-Base-Docker-Llama3
cd Local-AI-Knowledge-Base-Docker-Llama3

# Start the stack
docker compose up -d

# Pull the models (only first time, ~5 GB total)
docker compose exec ollama ollama pull llama3
docker compose exec ollama ollama pull mxbai-embed-large

# Start the Streamlit UI
docker compose exec app streamlit run web_ui.py
```

Open `http://localhost:8501`. Drop documents into `./knowledge_base/`,
click **🔄 Re-Ingest**, and start chatting.

> The Pro version replaces all of the above with a single `start.sh`
> or `start.bat` that handles everything including the model pulls.

---

## 🛠️ Architecture

```
   You ──► [Embedding model] ──► vector ──► ChromaDB
                                                │
                                                ▼
   Top-K matching chunks ◄──────  similarity search
            │
            ▼
   [Llama 3 + chunks as context] ──► Answer with citations ──► You
```

Three Docker containers:

| Container | What it does |
|-----------|--------------|
| **ollama** | Runs Llama 3 (or any other Ollama-compatible model) on GPU/CPU |
| **chromadb** | Vector database for semantic similarity search |
| **app** | Streamlit web UI for file management + chat interface |

---

## 🤖 Supported Models

Any model on [ollama.com/library](https://ollama.com/library) works.
Common choices:

| Model | Size | Speed | Quality | Best for |
|---|---:|---|---|---|
| `llama3` | 4.7 GB | Medium | High | Default — good balance |
| `llama3.1` | 4.7 GB | Medium | Higher | Newer than llama3 |
| `phi3` | 2.3 GB | Fast | Decent | Weak hardware (8 GB RAM) |
| `mistral` | 4.1 GB | Medium | Good | Multilingual |
| `qwen2.5` | 4.7 GB | Medium | High | Strong Chinese support |

---

## 📚 Related reading

- [**Local RAG with Llama 3 & Docker: Build an Offline Second Brain (No OpenAI)**](https://dev.to/philyeh/how-i-built-a-100-offline-second-brain-for-engineering-docs-using-docker-llama-3-no-openai-4gcj)
  — my Dev.to article (11 reactions, 6 comments) explaining the
  architecture decisions

---

## 🛡️ When to use local AI vs ChatGPT

| Concern | ChatGPT Plus | This Stack |
|---------|---|---|
| Cost | $20/month forever | $59 once (Pro) |
| Sends your private docs to OpenAI | Yes | **No** |
| Works offline | No | **Yes** |
| Per-query token costs | Yes (API) | Free |
| Compliance for regulated data | Tricky | Easy |
| Customize the prompt persona | Limited | Edit one file |
| Run on a server for your team | Pay per seat | Just expose port 8501 |

For **most use cases**, ChatGPT is fine. For these, local AI is much better:

- Confidential business documents (contracts, customer data, internal memos)
- Regulated industries (finance, healthcare, legal, defense)
- Field deployments with limited internet
- Cost-sensitive heavy use (automated pipelines, bulk Q&A)

---

## 📥 Get the Pro version

The Community Edition is fully functional and free. The
**[Pro version](https://philyeh.gumroad.com)** adds the production polish
that turns this from a "weekend project" into a "deploy-it-for-the-team"
tool: one-click setup, environment-driven config, source citations,
proper Dockerfile, and a commercial license.

| Product | Price | Link |
|---|---:|---|
| 🔒 **Private ChatGPT Stack** (this tool, Pro edition) | $59 | [Buy](https://philyeh.gumroad.com) |
| 🚛 **J1939 Sniffer Pro** | $59 | [Buy](https://philyeh.gumroad.com) |
| ⚙️ **Modbus Logger Pro** | $49 | [Buy](https://philyeh.gumroad.com) |
| 📡 **MQTT Logger Pro** | $39 | [Buy](https://philyeh.gumroad.com) |
| 🏭 **EtherNet/IP Study Kit** | $29 | [Buy](https://philyeh.gumroad.com) |
| 📦 **Industrial Python Toolkit Bundle** (4 tools, save $47) | **$129** | [Buy](https://philyeh.gumroad.com) |
| 📊 **CSV Dashboard** (free companion tool) | $0 | [Download](https://philyeh.gumroad.com) |

---

## ✉️ Contact & Support

- **Issues:** Use [GitHub Issues](https://github.com/PhilYeh1212/Local-AI-Knowledge-Base-Docker-Llama3/issues)
  for bug reports of the Community Edition
- **Custom integrations / enterprise:** Contact me via Gumroad
- **Email:** pokhts@gmail.com

---

## 📫 About

**Phil Yeh** — Senior Automation Engineer & Top Docker Author on Dev.to.
Based in Taiwan. I build Python tools for Industrial IoT, CAN Bus, and
Local AI.

- 🛒 **Store:** [philyeh.gumroad.com](https://philyeh.gumroad.com)
- ✍️ **Blog:** [dev.to/philyeh](https://dev.to/philyeh)

---

## 📝 License

The Community Edition in this repository is free for personal and
educational use. For commercial use (client projects, internal company
tools, products you sell), please get the **[Pro Edition](https://philyeh.gumroad.com)**
which includes a proper commercial license.

If this project helped you, please give it a ⭐ to support the
development. **Thank you to the 13 of you who already starred!** 🙏

---

<sub>**Keywords:** Local AI, RAG, Llama 3, Ollama, ChatGPT alternative,
private AI, Docker, self-hosted, offline AI, on-premises LLM, ChromaDB,
LangChain, Streamlit, knowledge base, document Q&A, vector database,
embeddings</sub>
