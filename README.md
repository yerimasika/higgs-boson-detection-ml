# Higgs Boson Detection with Machine Learning

This repository presents an applied **machine learning project** focused on the detection of the **Higgs boson** using simulated collision data from the **ATLAS experiment at CERN**.  
The project explores how supervised learning models can distinguish rare signal events from overwhelming background noise in a highly imbalanced, high-dimensional setting.

This work was developed as part of an academic project combining **data science, statistics, and applied machine learning**.

---

## Project Context

The Higgs boson is a fundamental particle whose experimental detection is challenging due to:
- its extremely short lifetime,
- the rarity of its production,
- and the large amount of background events that mimic its signature.

Human intuition and simple thresholds are insufficient to separate signal from background.  
Machine learning models are therefore used to exploit **subtle multivariate correlations** across many physical features.

---

## Dataset

- **Source**: CERN Open Data Portal (ATLAS Higgs Challenge)
- **Observations**: ~818,000 simulated collision events
- **Features**: 30 numerical variables describing kinematic and detector-level measurements
- **Target**:
  - `1` → signal (potential Higgs event)
  - `0` → background (Standard Model processes)

Missing values are encoded as `-999` and treated via imputation.

The full dataset is not stored in this repository due to size constraints.  
Dataset link: http://opendata.cern.ch/record/328

---

## Methodology

### 1. Data Preprocessing
- Removal of non-informative columns
- Binary encoding of the target variable
- Imputation of missing values
- Feature scaling using Min-Max normalization
- Careful handling of outliers (kept, as they may correspond to rare physical events)

### 2. Exploratory Analysis
- Univariate and bivariate analysis
- Comparison of signal vs background distributions
- Visualization of subtle structural differences between classes

### 3. Models Implemented

**Baseline models**
- Decision Tree
- Logistic Regression
- Naive Bayes

**Ensemble methods**
- Random Forest
- Bagging (Logistic Regression, Naive Bayes)
- AdaBoost
- Gradient Boosting

**Class imbalance strategies**
- No rebalancing (baseline)
- Under-sampling
- Over-sampling
- SMOTE
- Borderline-SMOTE

Models are evaluated using **Accuracy**, **F1-score**, and **confusion matrices**, with attention to the trade-off between performance and computational cost.

---

## Key Results

- Ensemble methods based on decision trees (Random Forest, Boosting) achieve the best performance
- Random Forest provides a strong balance between accuracy, robustness, and computation time
- Rebalancing techniques improve detection of the rare signal class (F1-score)
- SMOTE-based methods improve recall at the cost of higher computational complexity
- Linear and probabilistic models are fast but limited in expressive power

---

## Technologies Used

- Python
- Pandas / NumPy
- Scikit-learn
- Imbalanced-learn
- Matplotlib / Seaborn
- Jupyter Notebook

---

## Repository Structure

```
├── Code/higgs-boson-detection.ipynb     # Main notebook (EDA, models, evaluation)
├── higgs-boson-detection.pdf           # Full project report
├── README.md
```


---

## Why This Project Matters

This project demonstrates the ability to:
- Work with **large-scale, noisy, real-world datasets**
- Handle **strong class imbalance**
- Compare classical ML models with ensemble methods
- Reason about **performance vs interpretability vs computational cost**
- Apply data science techniques to **scientific discovery**

It reflects my interest in using machine learning to extract meaningful signals from complex systems.

---

## Author

**Sika**  
Data Scientist | Machine Learning & Applied AI  

More of my work is available on my GitHub profile.

---

## Notes

This repository is shared for educational and portfolio purposes.  
Feedback and discussions are welcome.
