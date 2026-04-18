# Regression Language Model (RLM)

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Parameters](https://img.shields.io/badge/parameters-424K-green)
![R²](https://img.shields.io/badge/R%C2%B2-0.74-orange)

A custom, high-efficiency Transformer-based regression model designed to predict continuous values from sequence data. This project explores how architectural optimization can achieve high performance (R²=0.74) on extremely small datasets (15K samples) while maintaining a minimal parameter footprint.

## 🔬 Research Overview

The core objective of this project is to demonstrate that massive-scale models like BERT are not always necessary for high-quality sequence regression. By optimizing the **attention structure**, **tokenization strategy**, and **positional encoding**, this RLM achieves competitive results with a fraction of the computational overhead.

### Key Performance Metrics
| Metric | RLM (This Project) | BERT-base (Comparison) | Improvement |
| :--- | :--- | :--- | :--- |
| **Parameters** | 424,000 (424K) | 110,000,000 (110M) | **~260× smaller** |
| **Inference Speed** | 1.0x (Baseline) | 4.5x slower | **4.5× faster** |
| **Training Data** | 15,000 samples | Pre-trained on Billions | **Extreme Efficiency** |
| **Accuracy** | **0.74 R²** | - | - |

## 🏗️ Architectural Innovation

This model diverges from standard Transformer implementations in three critical areas, making it uniquely suited for **low-resource environments** (specifically targeted toward Indian language modeling):

### 1. Tokenization Strategy
Standard tokenizers (like WordPiece or BPE) often struggle with morphologically rich Indian languages or small datasets, leading to out-of-vocabulary (OOV) issues. This project utilizes a [Custom Strategy - e.g., Character-level or Specialized Subword] approach that maximizes semantic density while keeping the embedding layer small.

### 2. Attention Structure
By utilizing a [Specify Structure - e.g., Localized or Sparse] attention mechanism, the model focuses on the most relevant contextual dependencies. This reduces the quadratic complexity typically associated with self-attention, enabling faster inference and lower memory consumption without sacrificing the model's ability to capture long-range sequence relationships.

### 3. Positional Encoding
Unlike fixed sinusoidal encodings which may not capture nuances in short, high-density sequences, this model implements [Specify Type - e.g., Learned or Rotary] positional encodings. This allows the model to better adapt to the specific syntax and structure of the input data, which is vital for the low-resource linguistic patterns found in Indic scripts.

## 🇮🇳 Application: Low-Resource Indian Languages

The efficiency of this 424K parameter architecture provides a blueprint for **low-resource NLP**. Most Indian languages suffer from a lack of massive digitized corpora required to train multi-billion parameter models. 

The success of this RLM on just 15K samples suggests that:
- **Feasibility:** High-performing models can be built for languages with limited data.
- **Accessibility:** The 4.5× faster inference allows these models to run on edge devices and low-tier hardware common in diverse geographic regions.
- **Transferability:** The architectural choices made here (specifically the tokenization and encoding) are directly applicable to the unique phonetic and grammatical structures of Indian languages.

## 🚀 Getting Started

### Requirements
- Python 3.8+
- PyTorch / TensorFlow [Specify your framework]
- NumPy, Scikit-learn

### Installation
```bash
git clone [https://github.com/aryanference/Regression-Language-Model-RLM-.git](https://github.com/aryanference/Regression-Language-Model-RLM-.git)
cd Regression-Language-Model-RLM-
pip install -r requirements.txt
