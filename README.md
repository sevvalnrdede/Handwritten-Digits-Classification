# 🖋️ Handwritten Digits Classification

This project focuses on the classification of handwritten digits (0-9) by evaluating and comparing three prominent machine learning algorithms: **Support Vector Machines (SVM)**, **Decision Trees (DT)**, and **Random Forest (RF)**. The models are trained and tested on the benchmark Pen-Digits dataset to determine the most accurate approach for spatial stroke coordinate classification.

---

## 📌 Project Overview
Handwritten digit recognition is a foundational problem in automated computer vision and computational intelligence. In this project, an end-to-end Machine Learning pipeline is established[cite: 2]. The pipeline processes dynamic sequential stroke coordinates recorded from a digital pressure-sensitive tablet, resamples the data into spatial vectors, performs exploratory data analysis, applies feature scaling, and tunes multiple models to determine classification limits.

---

## 📊 Dataset Specifications
* **Dataset File:** `pendigits_txt.csv`
* **Data Sources:** 
  1. [TÜBİTAK Journal Research Article](https://journals.tubitak.gov.tr/cgi/viewcontent.cgi?article=3717&context=elektrik)
  2. [UCI Machine Learning Repository: Pen-Based Recognition of Handwritten Digits](https://archive.ics.uci.edu/dataset/81/pen+based+recognition+of+handwritten+digits)
* **Data Collection:** Total samples are gathered from 44 unique writers (250 digit strokes each) using a WACOM PL-100V pressure-sensitive tablet with a sampling rate of 100 milliseconds.
* **Features:** Contains 16 spatial integer features normalized in the `0` to `100` range to make them invariant to scaling and translations[cite: 1]. The 16 features represent 8 sequentially sampled spatial coordinates—$(X_1, Y_1)$ through $(X_8, Y_8)$—mapping the left-to-right ($X$) and up-and-down ($Y$) paths of the pen trace points.
* **Target:** 10 distinct multi-class labels representing digit categories from `0` to `9`

---

## 🛠️ Technology Stack & Dependencies
* **Programming Language:** Python
* **Data Wrangling:** NumPy, Pandas
* **Data Visualization:** Matplotlib, Seaborn
* **Modeling & Metrics:** Scikit-Learn

---

## 🚀 Machine Learning Implementation Pipeline

### 1. Exploratory Data Analysis (EDA)
* Reviewed class frequency weights to ensure target distributions (`0-9`) are balanced across the dataset.
* Plotted feature correlation heatmaps to observe coordinate trace patterns.
* Visualized spatial sample coordinates mapped to sequential strokes.

### 2. Data Preprocessing
* Performed train-test splits (`80%` training, `20%` test boundary).
* Applied standard normalization transformations using `StandardScaler` to uniform the 16 coordinate feature distributions
### 3. Classification Modeling
Implemented three benchmark architectures:
* **Support Vector Machine (SVM):** Configured via Non-linear Radial Basis Function (`rbf`) kernel optimizer.
* **Decision Tree (DT):** Configured via iterative splitting depth parameters.
* **Random Forest (RF):** Implemented via multi-ensemble ensemble bootstrap architectures.

### 4. Evaluation
* Generated classification reports including precision, recall, and F1-score indicators.
* Built confusion matrices to visually pinpoint overlapping digit classification faults.

---

## 📈 Model Performance & Comparisons

The performance metrics on the test dataset are summarized in the comparative analysis table below:

| Classification Algorithm | Accuracy | Weighted F1-Score | Performance Status |
| :--- | :---: | :---: | :---: |
| 🥇 **Support Vector Machine (SVM)** | **99.45%** | **99.45%** | **Best Classifier** |
| 🥈 **Random Forest (RF)** | 99.36% | 99.36% | Robust Ensemble |
| 🥉 **Decision Tree (DT)** | 96.54% | 96.54% | Baseline Tree |

### 🔍 Key Analytical Insights
* **Spatial Optimization Boundary:** The **SVM classifier achieved the highest accuracy of 99.45%**. Non-linear RBF kernel transformation easily mapped the interconnected spatial coordinates into structural clusters.
* **Variance Reduction:** Solo Decision Trees yielded a lower accuracy of 96.54% due to hyperparameter splitting constraints. However, **Random Forest successfully reduced this variance**, boosting the score to **99.36%**.

---

## 📁 Repository Structure
```text
├── data/
│   └── pendigits_txt.csv
├── notebooks/
│   └── SVM-DT-RF Project (Hand Written Digits).ipynb
├── .gitignore
└── README.md
