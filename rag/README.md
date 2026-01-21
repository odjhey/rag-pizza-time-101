# RAG (Retrieval-Augmented Generation)

Some scaffolding for trying some RAG with local models using Ollama and LlamaIndex!

## Tech Stack

 - **Ollama** - For local embedding and LLM inference (must be installed separately)
 - **LlamaIndex** - For document indexing and retrieval pipeline (from .venv)

## Getting Started

 1. Install dependencies:
    ```bash
    uv sync
    ```

 2. Pull required Ollama models:
    ```bash
    models/embeddinggemma/ollama-pull-model.sh
    models/gemma3/ollama-pull-model.sh
    ```

 3. Prepare datasets:
    ```bash
    cd datasets && make data-coco
    cd datasets && make data-chartqa
    ```

 4. Build vector index:
    Open `notebooks/explore.ipynb` and run the notebook cells interactively to build the storage index.

## Directory Structure

```
rag/
├── datasets/          # Source datasets with Makefile for data preparation
│   ├── Makefile       # Targets for downloading datasets
│   └── *.parquet      # Downloaded dataset files
├── models/
│   ├── embeddinggemma/
│   │   └── ollama-pull-model.sh
│   └── gemma3/
│       └── ollama-pull-model.sh
├── notebooks/         # Jupyter notebooks for exploration
│   └── explore.ipynb
├── storage/           # Vector index storage (gitignored)
├── main.py            # Entry point
├── pyproject.toml     # Project configuration
└── README.md          # This file
```

## Generated Artifacts

The following directories contain generated artifacts and are gitignored:

- `datasets/` - Prepared datasets from huggingface or other sources
- `storage/` - Vector indices built with LlamaIndex

Models can be pulled using the scripts in `models/` subdirectories:

```bash
models/embeddinggemma/ollama-pull-model.sh
models/gemma3/ollama-pull-model.sh
```

Datasets can be prepared using the Makefile in `datasets/`:

```bash
cd datasets && make data-coco
cd datasets && make data-chartqa
```
