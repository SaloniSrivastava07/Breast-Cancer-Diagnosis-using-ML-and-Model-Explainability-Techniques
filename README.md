# Breast Cancer Diagnosis using Machine Learning and Explainable AI

## About the Project
This project uses machine learning algorithms to classify breast tumors as benign or malignant using the Wisconsin Breast Cancer Diagnostic dataset.

LIME and SHAP are used to understand how different features influence the model's predictions.

## Models Used
- Support Vector Machine (SVM)
- Random Forest
- Gradient Boosting

## Explainable AI Techniques
- LIME
- SHAP

## Dataset
The project uses the Wisconsin Breast Cancer Diagnostic dataset, which contains 569 records and 30 numerical features.

Dataset: https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data

## Results
The reported test accuracies were:

- SVM: 98.25%
- Random Forest: 96.49%
- Gradient Boosting: 95.61%

SVM achieved the highest test accuracy, while Gradient Boosting showed the highest mean accuracy in the reported five-fold cross-validation.

## Technologies Used
Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, LIME and SHAP.

## How to Run
1. Download or clone this repository.
2. Install the required libraries using `pip install -r requirements.txt`.
3. Open `Breast_Cancer_Project.ipynb` in Jupyter Notebook or Google Colab.
4. Download the dataset and update the file path if necessary.
5. Run the notebook cells.

## Disclaimer
This project is for educational and research purposes only. It is not intended for clinical diagnosis.
