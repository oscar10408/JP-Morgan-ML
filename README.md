# JP Morgan ML Take-Home Assignment

This repository contains my submission for the JP Morgan machine learning take-home assignment. It includes both requested deliverables:

1. **Income classification**: predict whether an individual's income is above or below \$50K.
2. **Customer segmentation**: build an unsupervised segmentation framework that can support marketing use cases.

## Repository structure

```text
jp-morgan-ml-takehome/
├── README.md
├── requirements.txt
├── data/
│   ├── census-bureau.columns
│   └── census-bureau.data
├── notebooks/
│   ├── classification.ipynb
│   └── segmentation.ipynb
├── figures/
│   ├── PR Curve.png
│   ├── ROC Curve + Confusion matrix.png
│   ├── Prediction-threshold.png
│   ├── Important-features.png
│   ├── GMM(k=5).png
│   └── UMAP(30).png
└── docs/
    ├── ML-TakehomeProject.pdf
    ├── JP-Morgan-ML-Classification(2).pdf
    └── JP-Morgan-ML-Segmentation.pdf
```

## Environment setup

I used Python 3.11+ for this project.

### Option 1: create a virtual environment

```bash
python -m venv .venv
source .venv/bin/activate        # macOS / Linux
# .venv\Scripts\activate         # Windows
pip install -r requirements.txt
```

### Option 2: install directly

```bash
pip install -r requirements.txt
```

## How to run the project

### 1) Launch Jupyter

```bash
jupyter notebook
```

or

```bash
jupyter lab
```

### 2) Open the notebooks

Run the notebooks in the following order:

1. `notebooks/classification.ipynb`
2. `notebooks/segmentation.ipynb`

## Data paths

The notebooks expect the raw data files to be available locally. In this repository, they are already included under:

- `data/census-bureau.columns`
- `data/census-bureau.data`

If needed, update the file paths inside the notebooks so they point to the local `data/` folder.

## What each notebook contains

### `notebooks/classification.ipynb`
This notebook:
- loads and cleans the census dataset
- creates the binary target (`>50K` vs `<=50K`)
- compares multiple classification models
- evaluates performance using ROC-AUC, PR-AUC, threshold tuning, and confusion matrix analysis
- produces report-ready summary tables and figures

### `notebooks/segmentation.ipynb`
This notebook:
- prepares a clustering-specific feature set
- excludes label-related columns from segmentation
- applies preprocessing, dimensionality reduction, and clustering
- compares multiple clustering approaches
- profiles the final segments using numeric and categorical summaries
- generates visualization outputs for interpretation

## Expected outputs

Running the notebooks should reproduce the main tables and figures used in the submission, including:
- classification performance plots
- threshold analysis
- feature-importance visualization
- segmentation visualizations and segment profile summaries

## Notes

- The `census-bureau.data` file is relatively large, so the first full run may take a while.
- Some segmentation experiments, especially UMAP-based exploration on larger samples, can take noticeably longer than the classification workflow.
- The repository includes PDFs and figures for convenience, but the notebooks remain the main source for the full workflow.

## Deliverables included

This repository includes:
- the two main notebooks
- the raw data files used to run them
- a `requirements.txt` file for dependency installation
- figures and PDF files used in the written submission
- this README with setup and execution instructions
