# Exoplanet Atmospheric Retrieval using Machine Learning

This repository contains the machine learning implementation and experimental analysis associated with the research work  
**“Exoplanet Atmospheric Retrieval on Ariel Big Data Challenge dataset and WASP-39b using Machine Learning Techniques.”**

The project investigates the use of supervised regression models to perform atmospheric retrieval from exoplanet transmission spectra, an inverse problem traditionally solved using computationally expensive Bayesian methods.

---

## Research Objective
To evaluate whether classical and neural machine learning regressors can reliably estimate:
- Atmospheric gas abundances (H₂O, CO₂, CO, CH₄, NH₃)
- Planetary equilibrium temperature  

directly from transmission spectra, and to study how preprocessing choices affect model stability and generalization.

---

## Datasets
- **Ariel Big Challenge (ABC) Dataset**  
  Synthetic transmission spectra generated using radiative transfer models, used exclusively for training and validation.

- **JWST NIRSpec Observations of WASP-39b**  
  Real observational spectra used to test model generalization beyond synthetic data.

---

## Preprocessing Pipeline
The study places strong emphasis on preprocessing and spectral alignment:
- Wavelength interpolation to a common 52-bin grid
- Sample-wise normalization and feature scaling
- Feature augmentation using statistical descriptors
- Log-scaling of target variables

These steps were found to have a dominant impact on model performance.

---

## Machine Learning Models
The following supervised regression models were implemented and benchmarked under identical conditions:
- Multi-Layer Perceptron (MLP)
- Support Vector Regression (SVR)
- XGBoost Regression

Hyperparameter optimization was performed using Optuna where feasible.

---

## Key Findings
- Model performance is highly sensitive to preprocessing choices
- Standard scaling led to unstable or collapsed models
- XGBoost provided the most stable predictions and generalized best to JWST data
- Retrieved gas abundances for WASP-39b showed qualitative agreement with published astrophysical studies

---

## Technologies Used
- Python
- Scikit-learn
- XGBoost
- NumPy, Pandas
- Matplotlib
- Jupyter Notebook

---

## Authorship & Context
This repository represents an **academic research collaboration** conducted at  
**B.M.S. College of Engineering**, Department of Information Science and Engineering.

The work is intended for research exploration and comparative analysis rather than production deployment.

---

## Notes
Future extensions may include uncertainty quantification, noise-aware training, and physics-informed modeling to improve robustness across diverse planetary regimes.
