# Soybean Grain Yield Prediction

## Overview
This project aims to predict soybean grain yield (GY) using machine learning models. The dataset, sourced from a study by de Oliveira et al. (2023), includes 40 soybean cultivars and various farming conditions. The goal is to help farmers optimize crop yield by identifying key factors such as cultivar type, plant height, and pod insertion.

## Dataset
The dataset contains 320 rows and 11 features, including:
- **Cultivar:** Type of soybean cultivar (40 levels).
- **Season:** Growing season (1 or 2).
- **Repetition:** Number of replications (1 to 4).
- **Continuous Variables:** Plant height (PH), insertion of the first pod (IFP), number of legumes per plant (NLP), number of grains per plant (NGP), number of grains per legume (NGL), number of stems (NS), mass of 100 grains (MHG), and grain yield (GY).

## Methodology
1. **Data Exploration & Cleaning:**
   - Identified and removed outliers using z-scores.
   - Imputed missing values using column means.
   - Applied transformations (log, sqrt) to normalize data for linear models.
   - Conducted PCA to address multicollinearity.

2. **Model Development:**
   - **Multiple Regression:** Baseline model to establish linear relationships.
   - **Regression Tree:** Interpretable model providing actionable insights for farmers.
   - **Support Vector Machine (SVM):** Best-performing model with an RMSE of 277.

3. **Ensemble Models:**
   - **Homogeneous Ensemble (Bagging):** Improved regression tree performance by reducing RMSE.
   - **Heterogeneous Ensemble:** Combined multiple regression, regression tree, and SVM models.

## Results
- **SVM Model:** Achieved the lowest RMSE (277) and MAE, demonstrating its ability to handle complex, non-linear relationships.
- **Regression Tree:** Provided actionable insights, such as recommending specific cultivars and maintaining at least 5 stems per plant for optimal yield.
- **Homogeneous Ensemble (Bagging):** Outperformed the individual regression tree, reducing RMSE significantly.

## Key Insights
- Cultivars 6, 9, 10, 13, and 17 are recommended for optimal yield.
- Maintaining at least 5 stems per plant can significantly improve grain yield.
- SVM models are highly effective for predicting grain yield but lack interpretability compared to regression trees.

## Technologies Used
- **Languages:** R
- **Libraries:** `caret`, `dplyr`, `ggplot2`, `kernlab`, `rpart`, `factoextra`
- **Techniques:** Data cleaning, feature engineering, PCA, k-fold cross-validation, ensemble modeling

## Repository Structure
- `DassanayakeM.DA5030.Project.Rmd`: R Markdown file containing the full analysis.
- `README.md`: This file.

## How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/MerlinDassanayake/soybean_grain_yield_prediction.git

## References
- de Oliveira, B. R., et al. (2023). Dataset: Forty soybean cultivars from subsequent harvests. Trends in Agricultural and Environmental Sciences, e230005.
- UCI Machine Learning Repository: [Forty Soybean Cultivars Dataset](https://archive.ics.uci.edu/dataset/913/forty+soybean+cultivars+from+subsequent+harvests)
