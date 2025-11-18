# Local-AI-Knowledge-Base-Docker-Llama3
A production-ready, 100% offline RAG Knowledge Base using Docker, Llama 3, and Ollama. Chat with your documents privately. Enterprise architecture showcase.



# 🧠 Enterprise Local RAG: Private AI Knowledge Base (Docker + Llama 3)

[![Docker](https://img.shields.io/badge/Docker-Containerized-blue.svg)](https://www.docker.com/)
[![Llama 3](https://img.shields.io/badge/Model-Llama%203-blueviolet.svg)](https://ai.meta.com/llama/)
[![License](https://img.shields.io/badge/License-Commercial-green.svg)]()
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux-lightgrey.svg)]()

> **Stop sending your sensitive engineering data to the cloud.**
>
> This project provides a production-grade, **100% offline RAG (Retrieval-Augmented Generation)** architecture. It allows you to chat with your proprietary documents (PDF, TXT, Markdown) using a local LLM, ensuring absolute data privacy.

---

## 🏗️ System Architecture

This system is designed with a microservices architecture, fully containerized using **Docker Compose** for one-click deployment.

![System Architecture Diagram](images/architecture_diagram.png)
*(Place a diagram here showing: User -> Web UI -> Backend API -> ChromaDB <-> Ollama)*

### 🛠️ Tech Stack
* **LLM Inference:** [Ollama](https://ollama.com/) (Running **Meta Llama 3** 8B)
* **Embeddings:** `mxbai-embed-large` (State-of-the-art retrieval performance)
* **Vector Database:** [ChromaDB](https://www.trychroma.com/) (Persistent local storage)
* **Backend/Frontend:** Python + Streamlit (Optimized for RAG workflows)
* **Deployment:** Docker Compose (Isolated environment)

---

## ✨ Key Features

* **🔒 100% Privacy:** No data leaves your machine. No OpenAI API keys required. Zero monthly fees.
* **🚀 GPU Acceleration:** Native support for NVIDIA GPUs (CUDA) for lightning-fast inference.
* **📂 Smart Ingestion:** Automatically parses, chunks, and vectorizes PDF and text documents.
* **💬 Context-Aware Chat:** Remembers conversation history and retrieves relevant context from your knowledge base.
* **🐳 One-Click Setup:** No "dependency hell". Just run `docker-compose up -d`.

---

## 📸 Screenshots

### 1. Chat Interface (Streamlit)
![Chat UI](images/chat_demo.png)

### 2. Knowledge Base Management
![Ingestion Process](images/ingestion_demo.png)

---

## 💻 System Requirements

To run this system smoothly with Llama 3 (8B), the following hardware is recommended:

* **OS:** Windows 10/11 (WSL2) or Linux (Ubuntu)
* **RAM:** 16GB+ System Memory
* **GPU:** NVIDIA RTX 3060 (8GB VRAM) or higher recommended.
    * *Note: The system can run on CPU-only mode, but inference will be slower.*

---

## 📥 Get the Complete System

Building a stable RAG system from scratch takes weeks of configuration (handling Python dependencies, Vector DB connections, and Docker networking).

I have packaged the **Full Source Code**, **Docker Configuration**, and **Setup Guide** into a ready-to-deploy bundle.

### 📦 What's included in the Full Package?
* ✅ **Complete Source Code** (Python)
* ✅ **`docker-compose.yml`** (Production ready)
* ✅ **Embedding & Vectorization Logic**
* ✅ **UI/UX Implementation**
* ✅ **Premium Support Guide**

👉 **Download the System Here:** [**Get it on Gumroad ($299)**](https://pokhts.gumroad.com/l/senior-engineer-toolkit)

*(Instant Access. One-time payment. Lifetime usage.)*

---

## 👨‍💻 About the Author
**Phil Yeh** - Senior Automation & Systems Engineer.
Specializing in Hardware-Software Integration, Industrial Automation, and Local AI Solutions.

* [LinkedIn Profile](#)
* [My Gumroad Store](https://pokhts.gumroad.com/)

---
*Keywords: RAG, Llama 3, Ollama, Docker, Local AI, Private GPT, Knowledge Base, Python, Vector Database, ChromaDB, Source Code*
