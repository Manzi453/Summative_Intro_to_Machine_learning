# Telco Customer Churn Prediction: Classical ML vs. Deep Learning

A comparative machine learning project predicting customer churn in the
telecommunications sector, built for the Machine Learning Module Summative
Project. The pipeline implements four classical ML experiments (Scikit-learn)
and four deep learning experiments (TensorFlow/Keras — Sequential API,
Functional API, and `tf.data`), evaluated head-to-head on the same
preprocessed dataset.

## Project Status

The classical ML experiments (1-4) have been executed end-to-end on the real dataset; their
results in this repo (report, CSV, figures) are measured, not estimated. The deep learning
experiments (5-8) are fully implemented and verified for correctness in the notebook, using the
Sequential API, Functional API, and `tf.data`, but require you to run the notebook once
(2-4 minutes on Google Colab's free CPU tier) to produce their actual numbers, since they need a
TensorFlow runtime. **Run the notebook, then fill in the 4 DL rows** in
`reports/experiment_results_table.csv` and the bracketed placeholders in
`reports/Telco_Churn_Report.docx` (clearly marked `[run notebook]`) before submission.

## Problem & Mission Alignment

Customer churn — the loss of subscribers to competitors — is one of the
costliest problems in the telecom industry, where customer acquisition can
cost five to twenty-five times more than retention. This project asks: can
we predict, from account and service data alone, which customers are at risk
of leaving — and which modeling family (classical ML or deep learning) does
that better on a modest, mixed-type tabular dataset? This sits inside the
broader theme of using data-driven decision-making to support sustainable,
efficient business operations.

## Repository Structure

```
telco-churn-prediction/
├── README.md                          <- you are here
├── requirements.txt                   <- pinned dependencies for reproducibility
├── LICENSE
├── .gitignore
│
├── data/
│   └── WA_Fn-UseC_-Telco-Customer-Churn.csv   <- raw dataset (IBM sample, open source)
│
├── notebooks/
│   └── TelcoCustomerChurnPrediction.ipynb     <- full pipeline: EDA -> preprocessing ->
│                                                  4 ML experiments -> 4 DL experiments ->
│                                                  evaluation -> experiment table -> conclusions
│
├── reports/
│   ├── Telco_Churn_Report.docx        <- scholarly report (intro, lit review, methodology,
│   │                                      results, discussion, conclusion; IEEE citations)
│   ├── experiment_results_table.csv   <- the 8-experiment comparison table (4 ML rows measured,
│   │                                      4 DL rows to fill in after you run the notebook)
│   └── figures/                       <- figures referenced in the report
│       ├── fig1_target_overview.png        (generated)
│       ├── fig2_numeric_boxplots.png       (generated)
│       ├── fig3_categorical_churn.png      (generated)
│       ├── fig4_correlation_heatmap.png    (generated)
│       ├── fig5_feature_importance.png     (generated)
│       ├── fig6_confusion_matrices_ml.png  (generated)
│       ├── fig7_dl_training_curves.png     (export from notebook after running it)
│       ├── fig8_confusion_matrices_dl.png  (export from notebook after running it)
│       ├── fig9_roc_curves.png             (notebook version covers all 8 experiments;
│       │                                     fig9_roc_curves_ml.png here covers the 4 ML only)
│       ├── fig9_roc_curves_ml.png          (generated)
│       ├── fig10_performance_comparison.png (generated; ML-only version — re-export after DL runs)
│       └── fig11_learning_curve.png        (generated)
│
└── docs/
    └── video_link.md                  <- link to the 5-10 min presentation recording
```

## How This Maps to the Grading Rubric

| Rubric Criterion | Where to find it |
|---|---|
| Problem Definition, Data, & Mission Alignment | README (above) + Report §1 Introduction |
| Literature Review & Theoretical Grounding | Report §2 Literature Review (10+ IEEE-cited sources) |
| Data Preprocessing & Feature Engineering | Notebook §4 + Report §3 Methodology |
| Model Implementation & Optimization (2+ approaches, 7+ experiments) | Notebook §5 (ML, 4 experiments) + §8 (DL, 4 experiments) |
| Experiment/Result Table | Notebook §11 + `reports/experiment_results_table.csv` + Report §4 |
| Model Evaluation & Error Analysis | Notebook §9-13 (confusion matrices, ROC, learning curves) + Report §5 Discussion |
| Code Quality & Documentation | Notebook: modular functions, markdown before/after every cell, seeded, runs top-to-bottom |
| Academic Report Quality & Originality | `reports/Telco_Churn_Report.docx` |
| Demo Video & Communication | `docs/video_link.md` |

## Setup & Reproducibility

```bash
git clone <your-repo-url>
cd telco-churn-prediction
python -m venv venv && source venv/bin/activate
pip install -r requirements.txt
jupyter notebook notebooks/TelcoCustomerChurnPrediction.ipynb
```

All random operations (NumPy, Python's `random`, TensorFlow, the train/test
split) are seeded with `SEED = 42` for reproducibility. The notebook runs
top-to-bottom without manual intervention, provided the CSV is present at
`data/WA_Fn-UseC_-Telco-Customer-Churn.csv` (the notebook's first code cell
sets the relative path automatically).

## Dataset

**Source:** [IBM Telco Customer Churn dataset](https://www.kaggle.com/datasets/blastchar/telco-customer-churn),
distributed publicly on Kaggle, originally released by IBM as a sample
dataset for its Watson Analytics tool. 7,043 customer records, 21 columns
(19 features + customer ID + the `Churn` target), mixing demographic,
account, and service-usage attributes.

## Results Summary

Eight experiments were run: Logistic Regression, two Random Forest
configurations, Gradient Boosting, and four neural network architectures
(shallow Sequential, deep Sequential, dropout-regularized Sequential, and a
Functional-API model with batch normalization). Full per-experiment metrics
(accuracy, precision, recall, F1, ROC-AUC) are in
`reports/experiment_results_table.csv` and discussed in detail in the report.

## Author

[Your name] — [Your course / institution]
