## **Project Overview**
This repository contains the complete workflow and evidence for my CSCU9M5 Introduction to Machine Learning assignment. The project objective is to develop predictive models to classify whether forest fires will burn more than 4% of the area using historical data from Montesinho Park.

## **My Work Process**

### **Data Exploration & Understanding** 
- Loaded the `forestfires_classification.csv` dataset containing 517 samples and 13 features
- Analyzed class distribution: 292 severe fires (T), 225 non-severe fires (F)
- Studied the scientific meaning of fire weather indices (FWI system)

### **Data Preprocessing**
- Identified that the `rain` variable contained 98.5% zero values, causing extreme skewness (19.8)
- Applied `log(1+x)` transformation, reducing skewness to 14.1 (29% improvement)
- Encoded month and day as ordinal values
- Applied MinMax scaling to fire weather indices
- Standardized meteorological variables

### **Model Development**
- Selected three models: Random Forest, Support Vector Machine, and Neural Network
- Used Grid Search with 5-fold cross-validation for Random Forest and SVM
- Used Random Search (20 iterations, 5-fold CV) for Neural Network
- Optimized for F1-score to address class imbalance

### **Experimental Results**
- **Validation Set Performance**:
  - Random Forest: F1 = 0.871
  - SVM: F1 = 0.727
  - Neural Network: F1 = 0.795
- **Final Model Selection**: Random Forest (best validation performance)
- **Test Set Results** (n=78 unseen samples):
  - Accuracy: 0.897
  - Precision: 0.929
  - Recall: 0.886
  - F1-Score: 0.907

### **Key Insights**
- Most important features: DMC (25.6%) and DC (25.5%) representing fuel moisture and drought conditions
- Least useful feature: Rainfall (0.0%) due to 98.5% zero values lacking predictive power
- No spatial bias detected: X (2.6%) and Y (3.2%) coordinates showed minimal importance
- Good model interpretability: Random Forest provided clear feature importance scores
