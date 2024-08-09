
## Introduction

This project focuses on Part-of-Speech (POS) tagging using neural network architectures. The objective is to predict the POS tag for each word in a given corpus of documents. The workflow includes data preparation, word embedding using GloVe embeddings, development of a baseline model, experimentation with model variations, and conducting error analysis.

## Project Overview

### 1. Data Preparation

The corpus is downloaded and split into training, validation, and test sets. The data is structured into a DataFrame to facilitate further processing. The corpus utilized in this project is available at: [dependency_treebank.zip](https://raw.githubusercontent.com/nltk/nltk_data/gh-pages/packages/corpora/dependency_treebank.zip).

### 2. Word Embedding

GloVe embeddings are employed as the sole input feature for the models. Out-of-vocabulary (OOV) words are handled by assigning static embeddings, such as random embeddings or placeholders.

### 3. Model Development

A baseline model is established using a simple neural architecture that includes a Bidirectional LSTM layer followed by a Dense layer. Several architectural variations are explored, such as replacing the LSTM with a GRU, adding an extra LSTM layer, or incorporating an additional Dense layer. Hyperparameter tuning is performed based on validation set performance.

### 4. Model Evaluation

The evaluation process involves selecting the two best-performing models based on the validation set and then assessing them on the test set. The primary metric used for evaluation is the F1-Macro score, calculated across various POS tags while excluding punctuation.

### 5. Error Analysis

An error analysis is conducted to identify the types of errors made by the models, explore potential causes, and suggest improvements.

## Data Splitting and Corpus

- **Corpus**: The project uses words and their associated POS tags from the corpus, ignoring the numeric values in the third column.
- **Data Splitting**:
  - Documents 1-100: Training set
  - Documents 101-150: Validation set
  - Documents 151-199: Test set

## Model Architecture and Features

- **Features**: GloVe embeddings are exclusively used as input features.
- **Baseline Model**: The baseline model is a two-layer architecture, consisting of a Bidirectional LSTM layer followed by a Dense layer.
- **Architectural Variations**:
  - Experiments include using GRU instead of LSTM.
  - Additional LSTM or Dense layers are explored.

## Evaluation Metrics

- **Primary Metric**: The main evaluation metric is the F1-Macro score, calculated without considering punctuation or symbol classes.
- **Training Metrics**: Accuracy is used during training to assess performance.

## Handling Out-of-Vocabulary (OOV) Terms

OOV words are managed by assigning static embeddings, such as random embeddings or placeholders, ensuring that the embeddings for test set OOV words are computed independently of the training and validation sets.
