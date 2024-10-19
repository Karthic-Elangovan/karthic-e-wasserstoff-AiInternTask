# Domain-Specific PDF Summarization & Keyword Extraction Pipeline

## Overview
This project implements a dynamic pipeline that processes multiple PDF documents, generates domain-specific summaries and keywords, and stores them in a MongoDB database. The system handles documents of varying lengths, prioritizes concurrency, speed, and efficiency, while avoiding the use of pre-built frameworks.

## Features
- **PDF Ingestion & Parsing**: Ingest and process PDFs of different lengths (short, medium, long).
- **Summarization**: Custom-built summarization logic based on document length.
- **Keyword Extraction**: Custom-built domain-specific keyword extraction.
- **MongoDB Storage**: Store document metadata, summaries, and keywords in MongoDB.
- **Concurrency**: Multi-threaded processing for speed and resource management.
- **Performance Metrics**: Benchmarking for concurrency, speed, and memory usage.

## Project Structure

pdf_pipeline/
├── README.md            # Documentation
├── Dockerfile            # Optional Docker setup
├── requirements.txt      # Dependencies (pymongo, PyMuPDF, etc.)
├── main.py               # Entry point for the pipeline
├── pdf_processor/
│   ├── __init__.py       # Init file for package
│   ├── pdf_ingestion.py  # Handles PDF ingestion and parsing
│   ├── summarizer.py     # Custom summarization logic
│   ├── keyword_extractor.py # Custom keyword extraction
│   ├── db_handler.py     # MongoDB operations (storing/updating documents)
│   └── error_handler.py  # Logs errors, handles corrupted PDFs
├── tests/
│   ├── test_ingestion.py # Unit tests for PDF ingestion
│   ├── test_summarizer.py # Unit tests for summarization
│   ├── test_keywords.py  # Unit tests for keyword extraction
│   └── test_db.py        # Unit tests for MongoDB operations
└── performance/
    ├── benchmark.py      # Scripts to measure performance, concurrency, and memory
    └── results/          # Store performance logs and reports


## Installation
1. **Clone the repository**:
   ```bash
   git clone <repository_url>
   cd pdf_pipeline
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up MongoDB**:
   Ensure MongoDB is running locally or provide connection details in `db_handler.py`.

4. **Run the pipeline**:
   ```bash
   python main.py
   ```

## Running Tests
To run unit tests:
```bash
pytest tests/
```

## Performance Testing
To run performance benchmarks:
```bash
python performance/benchmark.py
```

## Optional Docker Setup
For deployment using Docker, build the image:
```bash
docker build -t pdf_pipeline .
```

Run the container:
```bash
docker run -it pdf_pipeline
```

## Contributing
Feel free to open issues or pull requests if you'd like to contribute to the project!

