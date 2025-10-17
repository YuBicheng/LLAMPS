# Code Release Guide

## Step 1: Dataset Integration
The original dataset is not sorted chronologically but organized in time chunks. Integration is required for easier usage.  
Run `./Pre-processing/make_llamps_dataset.ipynb`

## Step 2: LLM Ranking and Analysis
Use LLM to process the data, score user texts, and perform analysis.  
Run `./llamps/Pre-processing/LLMprocess.py` separately for each of the following four paths. Running them concurrently can improve efficiency:
- `./llamps/Pre-processing/llamps-dataset/negative_examples_anonymous`
- `./llamps/Pre-processing/llamps-dataset/negative_examples_test`
- `./llamps/Pre-processing/llamps-dataset/positive_examples_anonymous`
- `./llamps/Pre-processing/llamps-dataset/positive_examples_test`

Note: Modify the `url` and `api_key` in `GPTRank.py` and `GPTAnalyze.py`. These are the interfaces for the large language model.

## Step 3: Dataset Preparation
Run ```./llamps/Pre-processing/process_sentence_embedding.py```
Run ```./llamps/Pre-processing/train_fast_dataset.py```

## Step 4: Training
Execute the following command in the terminal:  
```bash runme_combine16.sh```

## Step 5: ERDE Calculation and Visualization

### ERDE Score Calculation
- **File**: `llamps/erisk_infer_analyze.ipynb`
- Calculate the ERDE (Early Risk Detection Error) metric for model evaluation

### Sleep Pattern Visualization  
- **File**: `llamps/schedule_visulize.ipynb`
- Visualize and analyze sleep characteristics and patterns from the data

### Dimensionality Reduction Visualization
- **File**: `llamps/t-sne.ipynb`
- Apply t-SNE for dimensionality reduction and visualize high-dimensional data patterns
