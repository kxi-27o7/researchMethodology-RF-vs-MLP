# Random Forest vs Multilayer Perceptron Model

This study utilizes a labeled synthetic mobile money transaction dataset developed by the Makerere University Department of Computer Science and publicly available via Mendeley Data to compare Random Forest and Multilayer Perceptron Model performance in detecting mobile banking fraud. 

## Installation

Clone repository:

```bash
git clone https://github.com/kxi-27o7/researchMethodology-RF-vs-MLP
```

## Download essential files

The trained model and dataset is not included in this repository because it exceeds GitHub's file size limit.

**Download the dataset here:**

[(https://data.mendeley.com/datasets/zhj366m53p/2)]

**Download the model here:**

[(https://drive.google.com/drive/folders/1kgHz4LNbMl-mfm1qY7pa1EonwPWVvraR?usp=sharing)]

After downloading, place the database file inside:

```plaintext
dataset/synthetic_dataset
```

## Refined experiments

The staged notebooks are in `workspace/`:

1. `workspace/eda.ipynb` explores the raw synthetic transactions.
2. `workspace/feature_engineering.ipynb` builds the shared features and saves
   `results/featured_dataset/featured_144days.pkl`.
3. `workspace/train_model_logistic.ipynb`, `workspace/train_model_rf.ipynb`,
   and `workspace/train_model_mlp.ipynb` train Logistic Regression, Random
   Forest, and MLP. Each uses the same chronological split and feature-set
   ablations.
4. `workspace/evaluate_models.ipynb` chooses thresholds from validation
   predictions and displays Accuracy, Precision, Recall, Specificity,
   F1-Score, and MCC for the untouched final test period.

Open the notebooks in Jupyter or VS Code and run them in that order, with the
`code` folder as the working directory so the relative `dataset/` and
`results/` paths resolve. Models and validation/test scores are saved in
`results/logistic/`, `results/rf/`, and `results/mlp/`. Final metrics are
displayed directly in the evaluation notebook. All included transaction data
are synthetic, so this workflow does not establish real-world performance.

The split is train, six-step delay/validation, then test. The model trains on
all steps through 114. Steps 115–120 are both the six-step delay and the
validation period used to select the fraud threshold; steps 121–143 are the
untouched final test period.