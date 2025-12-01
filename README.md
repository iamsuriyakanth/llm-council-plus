# Open Cross-Evaluation for Language Models 🔍

Anonymous peer scoring across LLMs for toxicity, bias, hallucinations, and political tilt.

## 🌟 Concept

Inspired by [Karpathy's LLM Council](https://github.com/karpathy), this system uses **peer review** instead of a single judge model. Multiple AI models evaluate each other anonymously, producing democratic, transparent scores.

## ✨ Features

- **Multi-Model Evaluation**: 3+ diverse models from different providers
- **Anonymous Peer Review**: Models don't know which response is theirs
- **4-Criteria Scoring** (0-10 scale):
  - 🟢 **Toxicity**: Harmful or unsafe content
  - ⚖️ **Bias**: Neutral vs. biased viewpoint
  - 🤥 **Hallucination**: Factual accuracy
  - 🏛️ **Political Tilt**: Neutral vs. extreme leaning
- **Transparent Scoreboard**: All evaluations visible with reasoning

## 🏗️ How It Works

1. **Stage 1**: All models answer your question independently
2. **Stage 2**: Each model scores the others (anonymized as Response A, B, C...)
3. **Stage 3**: Scores are averaged and ranked

See [ARCHITECTURE.md](ARCHITECTURE.md) for technical details.

## 🛠️ Tech Stack

- **Backend**: Python, FastAPI, HTTPX
- **Frontend**: React, Vite
- **AI Provider**: [OpenRouter](https://openrouter.ai) (unified API for all models)

## 🚀 Quick Start

### Prerequisites
- Python 3.10+
- Node.js 18+
- OpenRouter API Key

### Setup

```bash
# Clone
git clone https://github.com/yourusername/llm-council-plus.git
cd llm-council-plus

# Backend
cd backend
echo "OPENROUTER_API_KEY=your_key_here" > .env
pip install -r requirements.txt

# Frontend
cd ../frontend
npm install

# Run
cd ..
./start.sh
```

Access at `http://localhost:5173`

## ⚙️ Configuration

Edit `backend/config.py` to change models:

```python
COUNCIL_MODELS = [
    "meta-llama/llama-3.3-70b-instruct:free",
    "x-ai/grok-4.1-fast:free",
    "openai/gpt-oss-20b:free",
]
```

## 🤝 Contributing

Pull requests welcome!

## 📄 License

MIT
