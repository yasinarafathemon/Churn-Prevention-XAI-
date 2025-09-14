# Consumer Behavior Analysis towards Sustainable Apparel

[![GitHub license](https://img.shields.io/github/license/yourusername/sustainable-apparel-analysis)](https://github.com/yourusername/sustainable-apparel-analysis/blob/main/LICENSE)
[![Python Version](https://img.shields.io/badge/Python-3.10-blue)](https://www.python.org/downloads/)

## Overview

This repository contains Jupyter notebooks for a university project (CSE303: Statistics for Data Science) analyzing consumer survey data on attitudes, awareness, and purchase intentions toward sustainable apparel made from organic and recycled materials. The analysis explores factors influencing buying behavior, including product knowledge, environmental awareness, and motivations.

Key objectives:
- Perform exploratory data analysis (EDA) to uncover patterns and correlations.
- Conduct statistical tests (e.g., regression, ANOVA) to model relationships.
- Apply machine learning (e.g., decision trees) and explainable AI (XAI) techniques (e.g., SHAP) for interpretable insights.

The dataset is derived from a survey of 384 respondents, covering demographics, Likert-scale responses on perceptions, and behavioral intentions.

## Project Structure

| File/Directory | Description |
|---------------|-------------|
| **Churn.ipynb** | Core statistical analysis: Data loading, correlation heatmaps, OLS regression (e.g., Product Knowledge vs. Buying Behavior), ANOVA for group differences (e.g., by age), and a basic Decision Tree classifier for prediction. Outputs include model summaries, plots, and accuracy metrics. |
| **XAI.ipynb** | EDA and XAI-focused analysis: Descriptive statistics, distribution histograms, correlation heatmaps (with emphasis on purchase intention), and setup for SHAP values to explain feature importance in consumer decisions. |
| **data/** | (Not included in repo) Survey data files: `DATA IN BRIEF -DATA.xlsx` and `Response.xlsx`. These contain raw responses (demographics, Likert scales for knowledge, awareness, motivations, and intentions). |
| **README.md** | This file! |
| **requirements.txt** | Python dependencies (see below). |

## Key Insights (from Notebooks)

- **Correlations**: Positive association between product knowledge (PK1) and buying behavior (BB1), implied by regression (correlation ≈ 0.49 based on R²=0.243). In the purchase intention analysis (B6), correlations with awareness features (e.g., B2, B3) are highlighted via targeted heatmaps, showing moderate to strong links (exact values visualized in notebook).
- **Regression**: Product knowledge (PK1) significantly predicts buying behavior (BB1) with R² = 0.243, F-statistic = 12.17, p < 0.001.
- **ANOVA**: No significant age-based differences in buying behavior (F = 1.636, p ≈ 0.20).
- **ML Performance**: Decision Tree accuracy = 0.25 (baseline; suggests need for more features or advanced models).
- **XAI**: SHAP library is installed and referenced for summary plots to identify top influential features (e.g., willingness to pay premiums, biodegradation awareness) on purchase intention.

Visuals include heatmaps, histograms, and regression plots for deeper interpretation.

## Setup & Installation

1. **Clone the Repository**:
   ```
   git clone https://github.com/yourusername/sustainable-apparel-analysis.git
   cd sustainable-apparel-analysis
   ```

2. **Create a Virtual Environment** (recommended):
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install Dependencies**:
   Copy the following into `requirements.txt` and run:
   ```
   pip install -r requirements.txt
   ```
   ```
   pandas==1.5.3
   numpy
   statsmodels
   seaborn
   matplotlib
   scikit-learn==1.2.2
   shap==0.44.0
   openpyxl  # For Excel reading
   scipy
   ```

4. **Add Data Files**:
   - Place `DATA IN BRIEF -DATA.xlsx` and `Response.xlsx` in a `data/` folder (create if needed).
   - These files are not committed due to privacy/size; obtain from the original survey source.

## Usage

1. **Run Notebooks**:
   - Open in Jupyter Lab/Colab: `jupyter lab` or upload to [Google Colab](https://colab.research.google.com).
   - Execute cells sequentially in `Churn.ipynb` for stats/ML, then `XAI.ipynb` for visualizations and correlations.
   - Note: Some cells assume Google Colab paths (e.g., `/content/`); adjust for local runs.

2. **Customization**:
   - Modify `selected_features` in `XAI.ipynb` to focus on specific variables.
   - Extend SHAP analysis by fitting a full model (e.g., Random Forest) and calling `shap.summary_plot()`.

3. **Reproduce Outputs**:
   - Expected: Heatmaps showing correlations >0.5 for awareness-intention pairs; regression p-values <0.05.

## Limitations & Future Work

- Dataset size (n=384) limits generalizability; add more samples.
- Models are simplistic—try Random Forest or XGBoost for better accuracy.
- Ethical note: Survey data anonymized; ensure compliance with data privacy (e.g., GDPR).
- Future: Integrate time-series if longitudinal data available; deploy as Streamlit app for interactive EDA.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Data sourced from a consumer survey on sustainable fashion (hypothetical/public domain).

- Thanks to libraries like SHAP for enabling interpretable AI!

---

*Last Updated: September 14, 2025*  
Questions? Open an issue or contact [your-email@example.com].
