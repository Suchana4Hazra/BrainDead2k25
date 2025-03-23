
---

# HybridSummarizer: A Transformer-Based Approach for Scientific Document Summarization

## Overview

This repository contains the code and pretrained models for HybridSummarizer, a transformer-based approach for scientific document summarization. Our model leverages contextual information from research papers, including categories and author information, along with the main content to generate concise, informative summaries. We utilize a modified BART-based architecture fine-tuned on ArXiv scientific paper data.

## Key Features

- **Hybrid Approach:** Incorporates both textual content and metadata (categories and authors) of scientific papers.
- **Transformer-Based:** Utilizes a modified BART architecture for abstractive summarization.
- **Fine-Tuned on ArXiv Data:** Trained and evaluated on a large dataset of scientific papers from the ArXiv repository.
- **Comprehensive Evaluation:** Assessed using ROUGE, BLEU, readability metrics, inference time, and memory usage.

## Methodology

1.  **Data Collection and Preprocessing:**
    -   Selection of relevant papers from the ArXiv JSON dataset.
    -   Extraction of key metadata: paper ID, title, abstract, authors, and categories.
    -   Split data into training (67\%) and validation (33\%) sets.
    -   Construction of input-output pairs for summarization:
        -   Input: `[CATEGORIES: {categories}] [AUTHORS: {authors}] {abstract}`
        -   Target/Output: paper title (as a summary)

2.  **Model Architecture:**
    -   Based on the BART architecture (specifically the `facebook/bart-large-cnn` variant).
    -   Fine-tuned on the preprocessed ArXiv dataset.
    -   Specifications:
        -   Maximum input sequence length: 512 tokens
        -   Maximum output sequence length: 128 tokens
        -   Learning rate: 2e-5
        -   Weight decay: 0.01
        -   Training epochs: 3
        -   Batch size: 4
        -   FP16 precision (when GPU available)



## Usage

Instructions on how to use the code and pretrained models will be provided soon.

## Future Work

-   Extending the model to handle full-text papers rather than just abstracts.
-   Incorporating citation information to better capture the impact and relevance of papers.
-   Developing domain-specific variants for different scientific fields.
-   Implementing fact-checking mechanisms to ensure accuracy in generated summaries.
-   Exploring multi-task learning approaches that combine summarization with related tasks like keyword extraction and citation prediction.




