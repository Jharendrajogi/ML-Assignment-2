# Machine Learning Assignment 2: Bagging, Boosting and Bias–Variance

**Student:** Jharendra Jogi  
**Roll Number:** M26MAC005  
**Course:** Machine Learning  
**Dataset:** Olivetti Faces  
**Random seed:** `26005`

## Overview

This repository contains the notebook and supporting artifacts for Machine Learning Assignment 2, *Bagging, Boosting and Bias–Variance on Face Recognition*. The experiments use decision trees, implement bagging and multiclass SAMME boosting, evaluate robustness to a masked image region and estimate bias and variance over repeated training-set resamples.

## Dataset and Experimental Setup

- **Dataset:** Olivetti Faces, with 400 images from 40 identities.
- **Input representation:** Raw flattened 64 × 64 pixel images; no PCA or other dimensionality reduction.
- **Data split:** For each identity, 6 images for training, 2 for validation, and 2 for testing.
- **Random seed:** `26018`, using the numeric characters in roll number `M26CSE018`.
- **Masked-image experiment:** The central image block at rows and columns 24–39 is set to zero in test images. Models are trained on clean images only.
- **Q1:** Decision-tree baseline and bootstrap bagging; compare accuracy, OOB accuracy, pairwise disagreement, vote margin, leaf occupancy, and confidence.
- **Q2:** From-scratch multiclass SAMME boosting; select depth and requested rounds using clean validation accuracy, compare training time and accuracy against bagging, and test masked-image robustness.
- **Q3:** Estimate bias squared and variance over 30 stratified training resamples, and compare shallow, selected, and deeper tree settings with 100-tree bagging ensembles.

## Saved Artifacts

- `X_train.npy.npz`, `X_val.npy.npz`, `X_test.npy.npz`: saved feature and label arrays for the three data partitions.
- `baseline_model.joblib`: selected single decision tree.
- `bagging_model.joblib`: bagged tree ensemble saved by the notebook. Verify that its ensemble size matches the final size selected using validation accuracy before submission.
- `boostingModel.joblib`: selected SAMME boosting model.
- `model_config.joblib` or `config.json`: configuration metadata. Ensure the values reflect the actual selected settings printed by the completed notebook rather than manually entered assumptions.
- `results/` and `figures/`: create these folders and export the final result tables and plots before submission.

The notebook is the main implementation and source of experiment logic. Some experiments—especially Q3's repeated refits—may take several minutes or longer. Use saved outputs to inspect results without retraining, but rerun from a clean kernel when verifying reproducibility.

## Environment Setup

Use Python and the libraries imported by the notebook, including NumPy, pandas, scikit-learn, Matplotlib, joblib, and joblib's parallel utilities where used. Record the actual package versions from the environment used for the final run in `requirements.txt`.

Create and activate a virtual environment (Git Bash on Windows):

```bash
python -m venv .venv
source .venv/Scripts/activate
```

Install the recorded dependencies:

```bash
pip install -r requirements.txt
```

## Running the Notebook

Open the notebook:

```bash
jupyter assignment.ipynb"
```

Run cells in order from a fresh kernel. The notebook downloads/loads the Olivetti Faces dataset through scikit-learn, creates the stratified split, trains and evaluates models, and runs the repeated bias–variance experiments. Keep the random seed and saved split fixed across all experiments.

## Reproducibility Checklist

- Save the exact train, validation, and test indices to `split_indices.npz` and reuse them for subsequent runs.
- Keep model selection based on validation accuracy; use the test set for final evaluation only.
- Train models only on clean images; apply the central mask only for robustness evaluation.
- Export final numerical tables to CSV and save the required figures to disk.
- Save the selected models and a configuration file containing the actual selected hyperparameters, ensemble sizes, boosting rounds, and random seed.
- Include `requirements.txt` with exact dependency versions and commands needed to reproduce the experiments.
- Check that every cell runs successfully from a clean kernel and that Q3 outputs are produced without errors.
- After pushing the final files, add the GitHub repository URL and final commit hash to the report.

## Main Entry Point

The main entry point is the Jupyter notebook. The exported model files, result tables, figures, saved split, and environment specification should accompany it in the final repository.
