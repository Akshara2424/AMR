# CODECURE AI Hackathon 2026 - TRACK B  
**Antibiotic Resistance Prediction (Microbiology + AI)**

**Team:** [Your Team Name]  
**Submission Date:** 31 March 2026  
**Track:** B - Antibiotic Resistance Prediction

## Problem Statement
Antimicrobial resistance is a global health crisis. This project predicts antibiotic resistance patterns from bacterial isolates and provides actionable treatment suggestions to support antibiotic stewardship.

**Exact requirements met:**
- Analyze bacterial resistance data
- Build classification models predicting resistance
- Explore feature importance
- Visualization of resistance gene networks
- Decision-support tool suggesting antibiotics (standout feature)

## Dataset Used
- **Primary Dataset**: Antimicrobial Resistance Dataset (Mendeley)  
  Link: https://data.mendeley.com/datasets/ccmrx8n7mk/1  
  - 5 antibiotics: Imipenem, Ceftazidime, Gentamycin, Augmentin, Ciprofloxacin  
  - Susceptibility outcomes: Resistant (R), Intermediate (I), Susceptible (S)  
  - Environmental/clinical isolates from Osun State, Nigeria

## Approach & Model
- **Model**: XGBoost (multi-label classification)  
- **Target**: Binary resistance prediction (Resistant vs Non-Resistant) for each antibiotic  
- **Evaluation**: Accuracy, F1-score, AUC-ROC  
- **Interpretability**: SHAP values for feature importance  
- **Network**: Phenotypic co-resistance network (NetworkX + Plotly) — visualizes which antibiotics tend to co-occur in resistance patterns

## Key Results & Insights
- Strong predictive performance on all 5 antibiotics  
- Top predictive features identified via SHAP (location, sample area, and cross-antibiotic patterns)  
- Clear co-resistance patterns observed (e.g., Augmentin & Ciprofloxacin frequently co-resist)  
- Biological insight: Model highlights multi-drug resistance hubs, enabling targeted stewardship

## Standout Feature – Interactive Decision-Support Tool
**Live Gradio App** that helps clinicians/researchers:
- Input isolate features (location, sample area)
- Get instant resistance prediction for all 5 antibiotics
- Receive ranked antibiotic recommendations with simple explanations
- View resistance network visualization

This directly addresses "Suggest potential treatment strategies" and is the key differentiator.

## Project Structure
codecure-trackb-antibiotic-mvp/
├── notebooks/          # Full Colab notebook (EDA + Model + SHAP + Gradio)
├── models/             # Trained XGBoost model (joblib)
├── visualizations/     # Heatmaps, SHAP plots, resistance network PNGs
├── app/                # Gradio decision-support tool
├── Dataset.xlsx        # Raw data (for reproducibility)
├── README.md
└── requirements.txt