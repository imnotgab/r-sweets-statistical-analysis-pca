# Sweets Nutritional Data: Statistical Analysis

This repository contains an advanced statistical analysis of the nutritional content of various sweets (classified as biscuits and cakes). The project focuses on rigorous data preprocessing, robust outlier detection, and dimensionality reduction techniques.

## Project Overview
The analysis explores how different nutritional variables (such as `energy_kcal`, `water`, `carbohydrates`, `sugar`, `dietary_fibres`, `fat`, `saturated fatty acids`, and `Na`) interact and how observations deviate from the norm. Standard statistical tools often fail in the presence of extreme outliers, so this project heavily utilizes **robust statistical methods** to uncover the true underlying patterns in the dataset.

## Key Analytical Steps
1. **Exploratory Data Analysis (EDA):**
   * Visualized distributions using Histograms and QQ-Plots.
   * Identified right-skewed trends across several variables (e.g., dietary fibres, sodium).
2. **Normality Testing & Data Transformation:**
   * Conducted Shapiro-Wilk tests to assess normality.
   * Applied the **Box-Cox transformation** to highly skewed variables (like dietary fibres) to stabilize variance and approximate normal distribution.
3. **Robust Outlier Detection:**
   * Compared classical tolerance ellipses with robust ellipses using the **Minimum Covariance Determinant (MCD)** estimator.
   * Utilized DD-plots (Mahalanobis distance vs. Robust distance) to successfully unmask outliers hidden by the classical approach.
4. **Principal Component Analysis (PCA):**
   * Performed classical PCA, using Scree plots and Kaiser's criterion to select 4 principal components that explain ~90% of the variance.
   * Interpreted biplots to understand relationships (e.g., the contrast between fat/energy and carbohydrates).
5. **Robust PCA (ROBPCA):**
   * Compared standard PCA with **Robust PCA** (`PcaHubert`).
   * Generated Outlier Maps (Score distance vs. Orthogonal distance) to properly flag bad leverage points and extreme observations that distort classical models.

## Technologies Used
* **Language:** R
* **Libraries:** `car`, `robustbase`, `ggplot2`, `moments`, `corrplot`, `rrcov`

## How to Run
1. Ensure `sweets_data.csv` is located in the root directory.
2. Open the R script or RMarkdown file (`.Rmd`).
3. Install any missing packages listed in the "Libraries" section.
