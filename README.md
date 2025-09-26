# 🎌 Anime Recommender System - LLMOps

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://python.org)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.28+-red.svg)](https://streamlit.io)
[![LangChain](https://img.shields.io/badge/LangChain-0.1+-green.svg)](https://langchain.com)
[![ChromaDB](https://img.shields.io/badge/ChromaDB-0.4+-purple.svg)](https://chromadb.ai)
[![Docker](https://img.shields.io/badge/Docker-Ready-2496ED.svg)](https://docker.com)
[![Kubernetes](https://img.shields.io/badge/Kubernetes-Ready-326CE5.svg)](https://kubernetes.io)

A production-ready **Large Language Model Operations (LLMOps)** system that provides intelligent anime recommendations using advanced NLP, vector embeddings, and modern MLOps practices.

## 🌟 Features

### 🤖 **AI-Powered Recommendations**
- **Semantic Search**: Vector-based similarity matching using HuggingFace embeddings
- **LLM Integration**: Powered by Groq API for natural language understanding
- **Context-Aware**: Analyzes genres, synopsis, and user preferences

### 🏗️ **Production-Ready Architecture**
- **Microservices**: Containerized with Docker
- **Scalable**: Kubernetes deployment ready
- **Monitoring**: Comprehensive logging and error handling
- **CI/CD**: Modern Python packaging with `pyproject.toml`

### 🎨 **User Experience**
- **Interactive Web UI**: Beautiful Streamlit interface
- **Real-time Processing**: Instant recommendations
- **Natural Language Queries**: "Find me a light-hearted school anime"

### 📊 **Data Pipeline**
- **Vector Database**: ChromaDB for efficient similarity search
- **Document Processing**: Intelligent text chunking and embedding
- **Data Persistence**: Persistent vector storage

## 🚀 Quick Start

### Prerequisites

- Python 3.10+
- Docker (optional)
- Kubernetes (optional)

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/anime-recommender-llmops.git
cd anime-recommender-llmops
```

2. **Create virtual environment**
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. **Install dependencies**
```bash
pip install -e .
```

4. **Set up environment variables**
```bash
cp .env.example .env
# Edit .env with your Groq API key
```

5. **Run the application**
```bash
streamlit run app/app.py
```

Visit `http://localhost:8501` to access the web interface.

## 🐳 Docker Deployment

### Build and Run
```bash
# Build the Docker image
docker build -t anime-recommender .

# Run the container
docker run -p 8501:8501 --env-file .env anime-recommender
```

### Docker Compose
```bash
docker-compose up -d
```

## ☸️ Kubernetes Deployment

Deploy to Kubernetes cluster:

```bash
# Apply Kubernetes manifests
kubectl apply -f llmops-k8s.yaml

# Check deployment status
kubectl get pods -l app=llmops
kubectl get services
```

## 📁 Project Structure

```
anime-recommender-llmops/
├── app/                    # Streamlit web application
│   ├── app.py             # Main web interface
│   └── __init__.py
├── src/                   # Core recommendation engine
│   ├── recommender.py     # LLM-powered recommendation logic
│   ├── vector_store.py    # ChromaDB vector operations
│   ├── data_loader.py     # Data processing utilities
│   └── prompt_template.py # LLM prompt engineering
├── pipeline/              # ML pipeline orchestration
│   ├── pipeline.py        # Main pipeline class
│   └── build_pipeline.py  # Pipeline construction
├── config/                # Configuration management
│   └── config.py          # Environment and model configs
├── utils/                 # Utility functions
│   ├── logger.py          # Logging configuration
│   └── custom_exception.py # Custom exception handling
├── data/                  # Dataset and vector database
│   ├── anime_updated.csv  # Anime dataset
│   └── chroma_db/         # Persistent vector store
├── logs/                  # Application logs
├── Dockerfile             # Container configuration
├── llmops-k8s.yaml        # Kubernetes manifests
├── pyproject.toml         # Modern Python packaging
└── requirements.txt       # Python dependencies
```

## 🔧 Configuration

### Environment Variables

Create a `.env` file with the following variables:

```env
# Groq API Configuration
GROQ_API_KEY=your_groq_api_key_here
MODEL_NAME=mixtral-8x7b-32768

# Vector Database
CHROMA_DB_PATH=./chroma_db
EMBEDDING_MODEL=all-MiniLM-L6-v2

# Application Settings
LOG_LEVEL=INFO
MAX_RECOMMENDATIONS=5
```

### Model Configuration

The system uses:
- **Embedding Model**: `all-MiniLM-L6-v2` (HuggingFace)
- **LLM**: Groq's Mixtral-8x7b (configurable)
- **Vector Database**: ChromaDB with persistent storage

## 🎯 Usage Examples

### Web Interface
1. Open the Streamlit app
2. Enter natural language queries like:
   - "Find me a romantic comedy anime"
   - "I want an action anime with great animation"
   - "Show me psychological thrillers"

### Programmatic Usage
```python
from pipeline.pipeline import AnimeRecommendationPipeline

# Initialize the pipeline
pipeline = AnimeRecommendationPipeline()

# Get recommendations
query = "light-hearted anime with school settings"
recommendations = pipeline.recommend(query)
print(recommendations)
```

## 🧪 Development

### Setup Development Environment
```bash
# Install development dependencies
pip install -e ".[dev]"

# Run linting
ruff check .
black .

# Run type checking
mypy src/

# Run tests
pytest tests/
```

### Building the Package
```bash
# Build distribution packages
python -m build

# Install from local build
pip install dist/anime_recommender-0.1.0-py3-none-any.whl
```

## 📊 Performance & Monitoring

### Logging
- **Structured Logging**: JSON-formatted logs with timestamps
- **Log Levels**: Configurable DEBUG, INFO, WARNING, ERROR
- **Log Rotation**: Automatic log file management

### Monitoring
- **Application Metrics**: Request latency, success rates
- **Resource Usage**: CPU, memory, and disk utilization
- **Error Tracking**: Comprehensive exception handling

## 🔒 Security

- **API Key Management**: Secure environment variable handling
- **Container Security**: Non-root user in Docker containers
- **Network Security**: Kubernetes network policies
- **Secret Management**: Kubernetes secrets for sensitive data

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines
- Follow PEP 8 style guidelines
- Add type hints to all functions
- Include comprehensive docstrings
- Write unit tests for new features
- Update documentation as needed

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **HuggingFace** for embedding models
- **Groq** for LLM API services
- **ChromaDB** for vector database
- **LangChain** for LLM orchestration
- **Streamlit** for web interface

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/Basswala/ANIME-RECOMMENDER-SYSTEM-LLMOPS/issues)
- **Discussions**: [GitHub Discussions](https://github.com/Basswala/ANIME-RECOMMENDER-SYSTEM-LLMOPS/discussions)
- **Documentation**: [Wiki](https://github.com/Basswala/ANIME-RECOMMENDER-SYSTEM-LLMOPS/wiki)

---

**Built with ❤️ for the anime community**
