# Time_series-Temporal Crime Pattern Analysis in the UK

## Project Overview

This project provides a comprehensive analysis of crime patterns across the United Kingdom using the UK Police Open Data portal. The analysis combines exploratory data analysis (EDA), predictive modeling, and spatial clustering to uncover temporal trends, geographic hotspots, and crime classification patterns.

### Key Objectives

- **Exploratory Data Analysis**: Understand data structure, quality, temporal patterns, spatial distributions, and crime-type variations
- **Crime Category Classification**: Predict crime types using gradient boosting models (XGBoost, LightGBM)
- **Spatial Hotspot Detection**: Identify crime concentration areas using density-based clustering (DBSCAN) and centroid-based clustering (K-Means)
- **Outcome Prediction**: Predict crime investigation outcomes using logistic regression and neural networks

---

## Repository Structure

```
Code_PoliceInvestigation_Project/
├── eda-for-police-dataset.ipynb              # Exploratory Data Analysis
├── model1-classification.ipynb               # Crime Category Classification
├── model2-clustering-outcome.ipynb           # Hotspot Detection & Outcome Prediction
└── README.md                                 # This file
```

---

## Notebooks Description

### 1. **eda-for-police-dataset.ipynb**
**Exploratory Data Analysis for UK Police Dataset**

This notebook provides a foundational analysis of the UK Police crime dataset:

- **Dataset Overview**: Structure, variables, data sources, and coverage
- **Data Quality**: Missing data analysis, data type validation, and cleaning requirements
- **Temporal Analysis**: Long-term trends, seasonality, monthly and yearly patterns
- **Spatial Analysis**: Geographic concentration, regional variations, and coordinate distributions
- **Crime Type Distribution**: Frequency analysis of offence categories
- **Feature Engineering**: Creation of temporal, spatial, and derived features for modeling

**Key Libraries**: pandas, numpy, matplotlib, seaborn, plotly, geopandas, pyarrow

---

### 2. **model1-classification.ipynb**
**Crime Category Classification Using Tree-Based Ensemble Methods**

This notebook implements supervised multi-class classification to predict crime types:

- **Task**: Multi-class classification with 14 crime categories
- **Models Used**:
  - **XGBoost**: Gradient Boosting with regularization
  - **LightGBM**: Fast Gradient Boosting Machine
  
- **Feature Engineering**:
  - Temporal features: Year, Month, Quarter, Season, Day of Week
  - Spatial features: Longitude, Latitude, Grid Cells (0.05° resolution)
  - Administrative features: Force area, LSOA code
  - Derived interactions: Spatio-temporal combinations

- **Class Imbalance Handling**: SMOTENC (oversampling) and Random Undersampling
- **Model Evaluation**: Accuracy, F1-Score, Balanced Accuracy, ROC-AUC, Feature Importance
- **Hyperparameter Tuning**: Optuna framework for optimization
- **Explainability**: SHAP values for model interpretability

**Key Libraries**: xgboost, lightgbm, scikit-learn, imbalanced-learn, optuna, shap

---

### 3. **model2-clustering-outcome.ipynb**
**Spatial Crime Hotspot Detection & Investigation Outcome Prediction**

This notebook addresses two tasks:

#### **Part A: Spatial Hotspot Detection (Unsupervised Learning)**
- **DBSCAN**: Density-based clustering for arbitrary-shaped crime hotspots
  - Automatic cluster discovery without pre-specifying number of clusters
  - Naturally handles isolated incidents as noise
  
- **K-Means**: Centroid-based clustering for deterministic hotspot allocation
  - Elbow method and Silhouette analysis for optimal cluster selection
  - Resource allocation planning at force-area level

#### **Part B: Crime Investigation Outcome Prediction (Supervised Learning)**
- **Task**: Binary classification - predict whether a crime will have an investigation outcome
- **Models Used**:
  - **Logistic Regression**: Interpretable linear baseline with coefficient-based insights
  - **MLP (Multilayer Perceptron)**: Neural network capturing non-linear interactions
  
- **Evaluation Metrics**: Accuracy, F1-Score, ROC-AUC, Precision-Recall curves
- **Visualization**: Interactive maps, confusion matrices, feature importance

**Key Libraries**: scikit-learn, hdbscan, folium, geopandas, contextily, plotly

---

## Data Source

**UK Police Open Data Portal**: https://data.police.uk/data/

The dataset includes:
- Crime records from multiple UK police forces
- Temporal coverage across multiple months/years
- Geographic coordinates (Longitude, Latitude)
- Crime classifications and investigation outcomes
- Lower-layer Super Output Area (LSOA) administrative data

---

## Dependencies

Install required packages:

```bash
pip install pandas numpy matplotlib seaborn plotly geopandas pyarrow contextily
pip install scikit-learn xgboost lightgbm optuna shap imbalanced-learn
pip install hdbscan scikit-learn-extra folium
```

---

## Usage

1. **Start with EDA**: Open `eda-for-police-dataset.ipynb` to understand data structure and patterns
2. **Classification Modeling**: Run `model1-classification.ipynb` for crime type prediction
3. **Clustering & Outcome**: Execute `model2-clustering-outcome.ipynb` for hotspot detection and outcome analysis

Each notebook is self-contained with:
- Environment setup and library installation
- Data loading and preprocessing
- Feature engineering
- Model training and evaluation
- Visualizations and interpretability analysis

---

## Key Findings & Insights

Through this analysis:
- Temporal patterns reveal seasonal and monthly variations in crime frequency
- Spatial clustering identifies geographic hotspots for targeted policing
- Crime type classification enables automated offense categorization
- Outcome prediction supports investigation prioritization

---

## Project Methodology

- **Data-Driven Approach**: Evidence-based analysis from official UK Police records
- **Academic Rigor**: Comprehensive EDA, proper train-test splits, cross-validation
- **Ensemble Methods**: Gradient boosting and neural networks for robust predictions
- **Explainability**: Feature importance and SHAP values for model transparency
- **Geospatial Analysis**: Integration of spatial data and interactive mapping

---

## Author

**Project**: Spatio-Temporal Crime Pattern Analysis  
**Dataset**: UK Police Open Data  
**Analysis Date**: 2026

---

## License

This project uses publicly available data from the UK Police Open Data portal. Please refer to the original data source for licensing information.

---

## Disclaimer

This analysis is for research and educational purposes. Crime data patterns should be interpreted with domain knowledge and may not capture all socioeconomic or demographic factors influencing crime occurrence.

---
