# AI-Accelerated-Drug-Discovery

This project leverages AI to accelerate the identification of drug candidates by predicting the bioactivity of chemical compounds against the acetylcholinesterase (AChE) protein. This protein plays a key role in neurological disorders, making it a prime target for drug discovery.

## Project Overview

- **Dataset:** Bioactivity data for AChE sourced from the [ChEMBL database](https://www.ebi.ac.uk/chembl/).
- **Objective:** Predict the bioactivity (pIC50) of chemical compounds, represented by SMILES strings, against the AChE protein to identify potential drug candidates.
- **Dataset after preprocessing:** `acetylcholinesterase_01_bioactivity_data_raw`
- **Techniques Used:**
  - Preprocessing of chemical structures using SMILES strings.
  - Feature extraction via molecular fingerprints (RDKit).
  - Models include Machine Learning (Random Forest, XGBoost) and Deep Learning (LSTM, GRU, ConvLSTM).

## What is SMILES?

- **SMILES**: Simplified Molecular Input Line Entry System.
- Encodes chemical compound structures in a text format.
- Used in computational chemistry to represent molecules.
- In this project, SMILES strings are converted into **molecular fingerprints** (binary vectors) for AI model input. 

## Methodology

1. **Data Preprocessing:**
   - Conversion of IC50 to pIC50 using `pIC50 = -log10(IC50)`.
   - Removal of missing data and generation of molecular fingerprints for model input.
   
2. **Models:**
   - **Machine Learning:** Linear Regression, Random Forest, XGBoost, Gradient Boosting.
   - **Deep Learning:** LSTM, GRU, ConvLSTM, BiLSTM.
   - **Optimization:** Hyperparameter tuning via Bayesian Optimization.

3. **Model Performance:**
   - Best-performing model: Gradient Boosting Regressor with R² = 0.73.
   - Challenges: High error rates, indicating room for model improvement.

## Deployment

- The best model was deployed using [Streamlit](https://streamlit.io/).
- Users can input SMILES strings to get predictions on the bioactivity (active/inactive) of compounds.
  
## Results

- **Best Model Performance:**
  - R² score: 0.73
  - MSE: 0.81
  - MAE: 0.64

## Dataset

The dataset is sourced from the [ChEMBL Database](https://www.ebi.ac.uk/chembl/) and can be accessed [here](https://drive.google.com/file/d/1ZZW3-jVW1hPicp4TAEc_TsFpZkcyRWkP/view?usp=sharing).

## Future Improvements

- Data enhancement to improve model accuracy.
- Further exploration of hybrid AI models for better predictions.
