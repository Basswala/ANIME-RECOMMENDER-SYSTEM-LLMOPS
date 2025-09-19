# Anime Recommender

A machine learning-based anime recommendation system built with Python.

## Features

- Vector-based anime recommendations using ChromaDB
- NLP-powered content analysis
- Streamlit web interface
- ML pipeline for data processing

## Installation

```bash
pip install anime-recommender
```

## Usage

```python
from src.recommender import AnimeRecommender

# Initialize recommender
recommender = AnimeRecommender()

# Get recommendations
recommendations = recommender.get_recommendations("Your favorite anime")
```

## Development

```bash
# Install in development mode
pip install -e .

# Build package
python -m build
```
