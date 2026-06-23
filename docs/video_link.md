# Presentation Video

**Link:** [paste your unlisted YouTube / Loom / Drive link here]

## Suggested 5–10 minute structure (matches the "Demo Video & Communication" rubric row)

1. **Problem & dataset (60–90s)** — What is churn, why it matters for a telecom
   business, why this dataset (7,043 customers, IBM Watson Analytics sample,
   moderate 73/27 class imbalance).
2. **Modeling approaches (90s)** — Briefly name the 4 classical ML models and
   4 deep learning architectures, and *why* both families were tried
   (interpretability vs. capacity to model feature interactions).
3. **Key design choices (90s)** — Why `class_weight='balanced'` instead of
   resampling, why StandardScaler, why the 3 engineered features
   (Charge_per_Tenure, Service_Count, Is_New_Customer), why EarlyStopping/
   ReduceLROnPlateau for the neural nets.
4. **Results walkthrough (2 min)** — Show the experiment table, point at the
   ROC curves and confusion matrices, name the best model by ROC-AUC, and
   explain *why* it likely won (e.g., tree ensembles handling non-linear
   tenure/contract interactions better than a shallow NN on a small, mostly
   one-hot feature space).
5. **Error analysis & limitations (60–90s)** — Which class is harder to
   predict (typically churners — the minority class), what the learning
   curve says about over/underfitting, and 1–2 honest dataset limitations
   (snapshot data with no time dimension, self-reported service columns,
   moderate imbalance).
6. **Wrap-up (30s)** — One concrete next step you'd try (e.g., SMOTE,
   threshold tuning for business cost asymmetry, or a wider architecture
   search).

Camera on, face visible, as required by the rubric.
