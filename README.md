# Breast Cancer Diagnosis Using Machine Learning and Explainable AI

A machine-learning study that classifies breast tumours as **benign** or **malignant** using the Wisconsin Breast Cancer Diagnostic dataset and explores model explanations with **LIME** and **SHAP**.

> **Important:** This is an academic project, not a medical device. Predictions must not be used for diagnosis or treatment decisions.

## Project overview

The project compares three supervised classification models:

- **Support Vector Machine (SVM)**
- **Random Forest**
- **Gradient Boosting**

The workflow includes data inspection, exploratory data analysis (EDA), preprocessing, an 80/20 train-test split, model evaluation, ROC and precision-recall curves, five-fold cross-validation, and explainability analysis.

- **LIME** is used to explain individual predictions for the three models.
- **SHAP** is used to explore feature contributions for the Gradient Boosting model.

## Repository structure

```text
breast-cancer-diagnosis-xai/
├── notebooks/
│   └── breast_cancer_diagnosis_xai.ipynb
├── report/
│   ├── breast_cancer_diagnosis_report_public.pdf
│   └── breast_cancer_diagnosis_report_public.docx
├── data/
│   └── README.md
├── results/
│   └── README.md
├── .gitignore
├── CITATION.cff
├── LICENSE
├── README.md
└── requirements.txt
```

## Dataset

This project uses the **Wisconsin Breast Cancer Diagnostic dataset**. The report describes 569 records, a diagnosis label, and 30 numerical features derived from fine-needle aspirate (FNA) images.

Download the dataset from Kaggle:

[Breast Cancer Wisconsin (Diagnostic) Data](https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data)

The notebook expects the CSV file to be named `Breast_cancer_dataset.csv`. See [`data/README.md`](data/README.md) for setup instructions. The dataset is not included in this repository.

## Getting started

### Option 1: Run in Google Colab

1. Upload or open `notebooks/breast_cancer_diagnosis_xai.ipynb` in Google Colab.
2. Download the CSV dataset from the Kaggle link above.
3. Upload the CSV to the Colab session and ensure its path matches the notebook's expected path (`/content/Breast_cancer_dataset.csv`).
4. Run the notebook cells from top to bottom. Install any missing dependencies if prompted.

### Option 2: Run locally

Python 3.10 or later is a reasonable starting point, although the notebook has not been verified across every Python version.

1. Clone this repository:
   ```bash
   git clone https://github.com/<your-username>/breast-cancer-diagnosis-xai.git
   cd breast-cancer-diagnosis-xai
   ```
2. Create and activate a virtual environment:
   ```bash
   python -m venv .venv
   ```
   Windows:
   ```bash
   .venv\Scripts\activate
   ```
   macOS/Linux:
   ```bash
   source .venv/bin/activate
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Put `Breast_cancer_dataset.csv` in the project root or update the CSV path in the notebook to match where you saved it.
5. Start Jupyter:
   ```bash
   jupyter notebook
   ```

## Methodology

1. Load and inspect the dataset.
2. Explore the diagnosis distribution and feature distributions.
3. Encode diagnosis labels (`M` = malignant, `B` = benign) and remove the ID column.
4. Split the data into training and test sets using an 80/20 split and `random_state=42`.
5. Standardize features for SVM; train Random Forest and Gradient Boosting on the unscaled feature data.
6. Evaluate models with accuracy, precision, recall, classification reports, confusion matrices, ROC curves, and precision-recall curves.
7. Run five-fold cross-validation.
8. Use LIME for local explanations and SHAP for Gradient Boosting feature-importance analysis.

## Results reported in the project report

The report records the following single train-test split results:

| Model | Accuracy | Precision | Recall |
|---|---:|---:|---:|
| SVM | 98.25% | 100.00% | 95.35% |
| Random Forest | 96.49% | 97.56% | 93.02% |
| Gradient Boosting | 95.61% | 95.24% | 93.02% |

The report's five-fold cross-validation summary gives mean accuracies of approximately 0.91 for SVM, 0.95 for Random Forest, and 0.96 for Gradient Boosting. These are values reported in the accompanying academic report; rerunning the notebook and evaluating the implementation should be used to verify reproducibility.

The report highlights `concave points_worst`, `concave points_mean`, `radius_worst`, and `perimeter_worst` among the important features in the Gradient Boosting SHAP analysis.

## Notes and limitations

- The notebook in this repository is a transcription/reconstruction of the code available in the supplied project PDF, rather than the original Colab notebook export. Review and run all cells before relying on the results.
- The CSV dataset is downloaded separately and is not committed here.
- Results are dependent on preprocessing, train/test splitting, library versions, and the exact dataset file.
- The report describes a research prototype; it does not establish clinical validity or readiness for real-world medical use.
- The dataset is not a substitute for clinical evaluation by qualified healthcare professionals.

## Project report

The `report/` folder contains a public-sharing copy of the project report. The student ID was removed from this copy before publishing.

## Citation

If you refer to this work, please cite the repository using the metadata in [`CITATION.cff`](CITATION.cff). Cite the original dataset and research sources listed in the report as appropriate.
