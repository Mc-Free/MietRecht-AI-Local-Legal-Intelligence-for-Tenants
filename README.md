# MietRecht-AI: Local-Legal-Intelligence-for-Tenants

# 🏠 MietRecht AI: Local Legal Intelligence for Tenants

![App Screenshot](assets/demo.png)

### *Simplifying German Rental Agreements through Local LLMs*

MietRecht AI is an open-source LegalTech tool that breaks down dense German rental contracts into plain language (DE and EN). Built with Llama Index, Ollama, and Gradio, it provides a private, secure, and instant way to audit leases and understand German rental law (Mietrecht).

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

🌍 Why It Matters

For many, especially expats in Germany, the housing market is a high-pressure environment. Tenants often sign 20-page documents in a foreign language without fully understanding the risks.

This project helps by:

 * Lowering Barriers: Translating complex legal jargon into actionable insights.

 * Risk Identification: Identifying "Red Flag" clauses (e.g., illegal renovation requirements) using a 0-10 risk scoring system.

 * Privacy-First AI: All processing happens locally. Your sensitive lease data is never uploaded to the cloud or used to train external models.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

🚀 Features

  * Fast Local Inference: Optimized using Llama 3.2 (1B) for real-time performance on consumer hardware.

  * Automated Clause Classification: Heuristic detection of Deposit, Termination, and Utility clauses.

  * Interactive Legal Chat: A persistent chat module to answer general questions about German law.

  * Citation Extraction: Automatically identifies § (Paragraph) references to the German Civil Code (BGB).

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

🛠️ Getting Started

   1. Setup Environment:
```bash
chmod +x setup_ollama.sh
./setup_ollama.sh
  ```
   2. Install Python Libraries:
  ```bash
  pip install -r requirements.txt
  ```
   3. Launch:
  ```bash
    python src/app.py
  ```

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

⚖️ Disclaimer

This tool is for educational and informational purposes only. It does not constitute formal legal advice. Always consult with a qualified legal professional or a Mieterverein (Tenants' Association) for binding legal guidance.


-------------------------------------------------------------------------------------------------------------------------------------------------------------------

📂 Project Structure

 ```bash
MietRecht-AI-Assistant/
├── setup_ollama.sh          # Automates system and model setup
├── requirements.txt         # Python dependencies
├── README.md                # Project documentation
├── src/
│   ├── app.py               # Main UI and entry point
│   ├── analyzer.py          # PDF logic and clause detection
│   ├── engine.py            # LLM & Embedding configurations
│   └── chat.py              # Conversation history management
└── samples/
    └── sample_lease.pdf     # A dummy file for users to test

 ```

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

📄 1. The Automation Script (setup_ollama.sh)

This script handles the "heavy lifting" of the environment setup.

```bash

#!/bin/bash
# setup_ollama.sh

echo "📦 Installing system dependencies..."
sudo apt-get update && sudo apt-get install -y zstd curl

echo "📥 Installing Ollama..."
curl -fsSL https://ollama.com/install.sh | sh

echo "🚀 Starting Ollama server in background..."
nohup ollama serve > ollama.log 2>&1 &

sleep 10 # Wait for server initialization

echo "🦙 Pulling Llama 3.2 1B (High-speed model)..."
ollama pull llama3.2:1b

echo "✅ Setup complete. Run 'pip install -r requirements.txt' next."


```

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

2. Dependency List (requirements.txt)

```bash
llama-index==0.10.0
llama-index-llms-ollama
llama-index-embeddings-huggingface
llama-index-readers-file
gradio
pypdf
requests

```
-------------------------------------------------------------------------------------------------------------------------------------------------------------------
## 👤 Author

Yann

Github: https://github.com/Mc-Free/ 

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

## ⭐ If this project inspires you, give it a star.





