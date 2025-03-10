# QuasID: Open-Source Model for Quasi-Identifier Detection

A machine learning model for systematic identification of Quasi-Identifiers (QIs) in datasets, built by fine-tuning Meta's Llama 3-8B model.

## Project Overview

QuasID addresses a gap in open-source privacy engineering tools by providing automated detection of Quasi-Identifiers in datasets. While tools exist for identifying personally identifiable information (PII), such as Capital One's Data Profiler, there was a lack of open-source tools specifically for QI detection.

### What are Quasi-Identifiers?

Quasi-Identifiers (QIs) are attributes or combinations of attributes that can potentially identify an individual when combined with other information. Common examples include:

- Demographic information (age, gender, ethnicity)
- Location data (zip code, city, country)
- Socioeconomic indicators (occupation, education level)
- Health-related information (height, weight)
- Temporal data (dates of significant events)
- Family-related information (marital status, number of children)
- Professional details (job title, years of experience)

## Technical Approach

### Model Architecture

- Base Model: Meta Llama 3-8B (8 billion parameters)
- Fine-tuning Method: Parameter-Efficient Fine-Tuning (PEFT) with Low-Rank Adaptation (LoRA)
- Optimization: Quantization using bitsandbytes library

### Dataset

The training data was sourced from UCI's Machine Learning Repository, using various datasets including:

- Predict Students' Dropout and Academic Success
- Student Performance
- Heart Disease
- Online Retail
- Heart Failure Clinical Records
- Bank Marketing

Fields were manually labeled based on established definitions of Quasi-Identifiers.

## Installation

### Environment Setup

1. Create a Python virtual environment:

```bash
python -m venv pytorch_env
source pytorch_env/bin/activate  # Linux/Mac
# or
pytorch_env\Scripts\activate     # Windows
```

2. Install required packages:

```bash
pip install -r requirements.txt
```

### Required Libraries

Key dependencies include:

- torch
- transformers
- datasets
- peft
- bitsandbytes
- scikit-learn
- pandas
- numpy

Full requirements are listed in the requirements.txt file.

## Usage

1. Ensure you have a valid Hugging Face account and access token
2. The notebook is organized into the following main sections:
   - Data preparation and loading
   - Model configuration and fine-tuning
   - Evaluation and testing

### Running the Notebook

1. Start Jupyter:

```bash
jupyter notebook
```

2. Open `QuasID.ipynb`
3. Follow the step-by-step sections in order

## Limitations and Challenges

1. Hardware Constraints:

   - Even with high-end consumer GPU, memory management was challenging
   - Multiple training iterations were required due to memory limitations
   - Long training and evaluation times

2. Dataset Challenges:
   - Limited variety in QI types across different datasets
   - Inconsistent data formats for similar fields
   - Manual labeling required for training data

## Contributing

We welcome contributions to improve the model's performance or expand its capabilities. Please feel free to submit pull requests or open issues for discussion.

## License

[Insert License Information]

## Acknowledgments

- UCI Machine Learning Repository for the datasets
- Meta for the Llama 3 model
- Hugging Face for their transformers library and infrastructure
