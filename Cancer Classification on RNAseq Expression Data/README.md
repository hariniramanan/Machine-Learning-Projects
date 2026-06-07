
# Multi-Class Tumor Classification Using RNA-Seq Gene Expression Data

## Project Overview

This project uses RNA-seq gene-expression data to classify tumor samples into different cancer types. The dataset used is the **Gene Expression Cancer RNA-Seq dataset from Kaggle**, which is a random extraction of the RNA-Seq HiSeq PANCAN dataset.

This is a supervised machine learning classification problem where each sample contains thousands of gene-expression features, and the target variable is the cancer type.

**Dataset:** Gene Expression Cancer RNA-Seq
**Source:** Kaggle
**Original data type:** RNA-Seq HiSeq PANCAN gene-expression data

The dataset contains gene-expression profiles across multiple cancer types:

* BRCA: Breast invasive carcinoma
* KIRC: Kidney renal clear cell carcinoma
* COAD: Colon adenocarcinoma
* LUAD: Lung adenocarcinoma
* PRAD: Prostate adenocarcinoma

The dataset contains:

* 801 samples
* 20,531 gene-expression features
* 5 cancer classes

The data is provided in two files:

```text
data.csv
labels.csv
```

`data.csv` contains the gene-expression values for each sample.

`labels.csv` contains the corresponding cancer type label for each sample.

## Project Objective

The objective of this project is to build a machine learning pipeline that can classify cancer types based on RNA-seq gene-expression profiles.

The project focuses on:
* Understanding class distribution
* Preprocessing RNA-seq expression data
* Feature scaling
* Feature selection
* Training multi-class classification models
* Evaluating model performance
* Comparing different machine learning algorithms
* Understanding overfitting in omics datasets

## Workflow

The project follows this workflow:

```text
1. Load the dataset
2. Inspect the structure of data.csv and labels.csv
3. Separate gene-expression features and cancer-type labels
4. Check sample-label alignment
5. Analyze class distribution
6. Split the dataset into training and testing sets
7. Apply feature scaling
8. Train baseline classification models
9. Evaluate models using classification metrics
10. Plot confusion matrices
11. Apply feature selection
12. Benchmark different models
13. Interpret the results
```

## Data Preparation

The gene-expression data contains one sample ID column and 20,531 gene-expression columns.

The sample ID column is removed before model training because it is not a biological feature.

```python
X = data.drop(columns=["Unnamed: 0"])
y = labels["Class"]
```

Here:

* `X` contains the gene-expression features
* `y` contains the cancer type labels

The sample IDs in `data.csv` and `labels.csv` are checked to make sure the rows are correctly aligned.

```python
(data["Unnamed: 0"] == labels["Unnamed: 0"]).all()
```

This step ensures that each gene-expression profile is matched with the correct cancer type.

## Exploratory Data Analysis

Exploratory analysis includes:

* Checking the shape of the dataset
* Checking missing values
* Viewing class distribution
* Understanding the number of samples per cancer type
* Visualizing class imbalance

## Machine Learning Models

The following models are tested and compared:

* Logistic Regression
* Random Forest Classifier
* Support Vector Machine
* K-Nearest Neighbors
* Gradient Boosting Classifier

These models were chosen to compare linear, nonlinear, distance-based, and tree-based approaches.

## Model Evaluation

Model performance is evaluated using:

* Accuracy
* Precision
* Recall
* F1-score
* Macro F1-score
* Weighted F1-score
* Confusion matrix

Macro F1-score is especially useful because it treats all cancer classes equally, regardless of class size.

Weighted F1-score accounts for class imbalance by weighting each class based on the number of samples.

## Expected Results

The expected outcome is that gene-expression profiles should be able to classify tumor type with strong performance because different cancer types have distinct molecular signatures.

However, careful validation is required because high-dimensional datasets can produce overly optimistic results if data leakage or overfitting occurs.

## Key Learning Outcomes

Through this project, I learned:

* How to work with high-dimensional RNA-seq gene-expression data
* How to prepare biological datasets for machine learning
* Why train-test splitting must happen before scaling and model fitting
* Why feature scaling matters for PCA, SVM, Logistic Regression, and KNN
* How PCA can reveal structure in gene-expression data
* How to train and evaluate multi-class classification models
* Why cross-validation is important in small-sample, high-feature datasets
* How feature selection can reduce noise and improve model interpretability
* How to interpret confusion matrices and classification reports
* Why high model accuracy must be interpreted carefully in omics datasets

## Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook

## How to Run the Project

Clone the repository:

```bash
git clone <repository-url>
cd gene-expression-cancer-classification
```

Install the required packages:

```bash
pip install -r requirements.txt
```

Open the Jupyter Notebook:

```bash
jupyter notebook
```

Run the notebook step by step.

## Requirements

Example `requirements.txt`:

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
jupyter
```

Limitations include:

* The dataset is a subset of a larger RNA-seq dataset
* The analysis does not include raw RNA-seq preprocessing
* Gene-expression values are treated as model-ready features
* Biological pathway analysis is not included in the initial version
* Feature importance should not be interpreted as causal biological evidence
* External validation on an independent dataset is not performed
