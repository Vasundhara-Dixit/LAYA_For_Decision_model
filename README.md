# LAYA for Decision Model

This repository contains the code, datasets, evaluation results, training checkpoints, and model weights for fine-tuning and evaluating the **LAYA Decision Model** (including PII decision modeling, classification, and validation).

---

## 📁 Repository Structure

```
.
├── LAYA_decision_model.ipynb   # Main notebook for training, data processing, and evaluation
├── data/                       # Train, validation, test, and OOD dataset splits (.jsonl)
├── figures/                    # Performance plots, ROC/PR curves, confusion matrices
├── final_metrics.csv           # Detailed validation, test, and OOD metrics across thresholds
├── history.json                # Training loss and epoch history
├── laya-fine-tuning/           # Laya fine-tuning framework, harness, templates, and evaluations
├── laya-pii-v3/                # Model weights, tokenizers, encoder configs, and checkpoint reports
│   ├── model.safetensors       # Final model weights (tracked via Git LFS)
│   ├── checkpoint_latest/      # Latest training checkpoint and weights (Git LFS)
│   ├── encoder/                # Encoder configuration
│   ├── tokenizer/              # Tokenizer files and configs
│   └── train_report.json       # Pre/post evaluation metrics and calibration results
└── naamapadam/                 # Indic benchmark dataset archive (hindi.zip)
```

---

## ⚡ Getting Started & Cloning

Because this repository contains large model weights (`*.safetensors`), **Git LFS (Large File Storage)** is required.

### 1. Install Git LFS
Ensure Git LFS is installed on your local machine:

```bash
git lfs install
```

### 2. Clone the Repository
Clone the repository using standard Git:

```bash
git clone https://github.com/Vasundhara-Dixit/LAYA_For_Decision_model.git
cd LAYA_For_Decision_model
```

If the large files are pointers after cloning, pull them using:
```bash
git lfs pull
```

---

## 📊 Evaluation Summary

Performance highlights across evaluation sets (from `final_metrics.csv`):

| Split | Threshold | Accuracy | Precision | Recall | Specificity | F1 Score | ROC AUC | PR AUC |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Validation** | @0.50 | 88.83% | 86.07% | 92.67% | 85.00% | 89.25% | 0.929 | 0.904 |
| **Test** | @0.50 | 89.50% | 89.90% | 89.00% | 90.00% | 89.45% | 0.947 | 0.954 |
| **Test (Natural)** | @0.50 | 88.91% | 91.93% | 89.29% | 88.35% | 90.59% | 0.950 | 0.967 |
| **OOD** | @0.78 | 90.00% | 91.67% | 84.62% | 94.12% | 88.00% | 0.973 | 0.971 |

---

## 🛠️ Usage

### Dependencies
Install the required Python packages:
```bash
pip install -q datasets huggingface_hub pandas pyarrow "transformers<5" laya
```

### Running the Notebook
Open and execute `LAYA_decision_model.ipynb` in Jupyter Notebook, VS Code, Google Colab, or Kaggle.
