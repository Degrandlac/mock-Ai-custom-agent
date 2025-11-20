# 🌍 Tecgrw AI Communication System

A modular, AI-powered communication platform integrating:

- 🎙️ **Automatic Speech Recognition (STT)**
- 🔊 **Text-to-Speech (TTS)**
- 🧠 **Language Understanding & Retrieval-Augmented Generation (RAG)**
- ☎️ **Interactive Voice Response (IVR)**

Each service runs independently using Docker for scalable, maintainable, and language-inclusive conversational AI across African languages.

---

## 🧭 System Architecture

application/
├── Api_server/ → Core logic (LLM, RAG, DB, embeddings)
├── ivr_tree_service/ → Interactive Voice Response (IVR) system
├── stt_service/ → Speech-to-Text (ASR) service
├── tts_service/ → Text-to-Speech synthesis
├── docker-compose.yml → Multi-service orchestration
└── requirements.txt → Global dependencies

### 🧠 Flow Diagram
Caller → IVR → STT → API (RAG + LLM) → TTS → IVR → Caller

---

## ⚙️ Features

### 🗣️ Speech-to-Text (STT)
- Fine-tuned multilingual **Automatic Speech Recognition** (ASR).
- Supports **Kinyarwanda** and other African languages.
- Converts real-time or recorded audio into accurate transcripts.

### 🔊 Text-to-Speech (TTS)
- Uses **Meta’s MMS model**, fine-tuned for **Kinyarwanda**.
- Converts natural text into speech.
- Includes post-processing for noise and distortion reduction.

### 🧠 API Server
- Hosts the **LLM service**, **RAG system**, and **vector DB integration**.
- Uses **African Cross-Lingua Embeddings** for multilingual understanding.
- Integrates **Tavily** for external search/context enhancement.

### ☎️ IVR Tree Service
- Interactive voice response system.
- Handles audio prompts and routing logic.
- Integrates TTS responses dynamically.

---

## 🐳 Docker Setup

### 🧱 Build and Run All Services

```bash
docker-compose up --build
This command spins up:

api_server

tts_service

stt_service

ivr_tree_service

Each runs in isolation with shared networking.
```

pip install -r requirements.txt
Caller
  ↓
IVR Service → (Audio → Text)
  ↓
STT Service → (Text Understanding)
  ↓
API Server (LLM + RAG)
  ↓
TTS Service → (Text → Audio)
  ↓
IVR Service → (Plays Response)
  ↓
Caller

