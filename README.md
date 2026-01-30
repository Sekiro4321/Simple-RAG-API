📌 Simple-RAG-API

A lightweight Retrieval-Augmented Generation (RAG) API that runs locally with a local LLM (via Ollama). Built for simplicity and ease of experimentation — ideal for learning how to build vector-based search + generation without cloud APIs.

🧪 You get a minimal RAG backend that loads a local model, ingests text, and serves responses via HTTP in a Docker container — no cloud bills.

🚀 Features

🧠 Local LLM support using Ollama

📊 Document embedding + retrieval pipeline

🛠️ Simple REST API powered by FastAPI (likely; adjust if you didn’t use FastAPI)

🐳 Docker support for easy deployment

🧪 Zero external dependencies (no OpenAI keys, no paid APIs)

📦 Clean folder structure (e.g., app.py, embed.py)

📥 Quick Start
🏗️ Clone it
git clone https://github.com/Sekiro4321/Simple-RAG-API.git
cd Simple-RAG-API

🐳 Build the Docker image
docker build -t simple-rag-api .

🚀 Run the API
docker run -p 8000:8000 simple-rag-api


Now your API should be live at http://localhost:8000.

📡 How It Works (High-Level)

Here’s the idea — no rocket science:

Embed incoming text using an embedding model in embed.py

Store vectors in memory (or a lightweight store)

Run a local LLM with Ollama to answer queries based on the nearest embeddings

Serve JSON responses through an HTTP API in app.py

This is basically a local RAG pipeline — simple, fast, and offline-friendly.

📄 API Endpoints

🎯 Adjust these if your code uses different routes — just drop in the actual ones.

Method	Endpoint	Description
GET	/health	Check server status
POST	/embed	Submit text to create embeddings
POST	/query	Ask a question and get a RAG-powered reply
🛠️ Configuration

No external API keys needed!

Just ensure:

Ollama is installed and running locally

The local model is available for your container

Example .env (if used):

MODEL_NAME=your_local_model_here
PORT=8000


(If you’re not using .env, keep configs in a config.py or similar.)

📦 Project Structure
Simple-RAG-API/
├── app.py          # RAG API server code
├── embed.py        # Embedding & vector logic
├── Dockerfile      # Container image build
├── k8s.txt         # Kubernetes example (optional)
└── README.md       # This file

🧪 Development

Want to work on the code locally?

Create a Python virtual env:

python3 -m venv venv
source venv/bin/activate


Install deps:

pip install -r requirements.txt


Run locally:

uvicorn app:app --reload --host 0.0.0.0 --port 8000


Then test with curl or Postman. 🚀

🧠 What This Is Great For

📚 Learning how RAG works end-to-end

🔒 Experimenting with local LLMs (no API bills)

🛠️ Building prototypes that don’t depend on cloud

🧑‍💻 Portfolio project to demo RAG basics
