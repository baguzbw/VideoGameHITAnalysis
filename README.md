# Video Game "Hit" Classification: Decision Tree vs Naive Bayes

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/baguzbw/VideoGameHITAnalysis/blob/main/Project_AI_VideoGame_Hit.ipynb)

## Goal

Predict whether a video game becomes a **Hit** (at least 1 million units sold) using only non-sales information such as genre, platform, publisher, age rating, and reviews. Two algorithms are compared: **Decision Tree** and **Naive Bayes**.

## Dataset

[Video Game Sales with Ratings](https://www.kaggle.com/datasets/rush4ratio/video-game-sales-with-ratings) (Kaggle), which combines VGChartz sales data with Metacritic reviews up to December 2016.

- 16,719 rows, 16 columns
- Only 12.4% of games are Hits, so the classes are imbalanced
- All sales columns are excluded from the features to prevent data leakage

## Results

| Metric | Baseline | Decision Tree | Naive Bayes |
|---|---|---|---|
| Accuracy (test set) | 0.876 | **0.900** | 0.856 |
| Precision | 0 | **0.690** | 0.431 |
| Recall | 0 | 0.354 | **0.499** |
| F1-score | 0 | **0.468** | 0.463 |
| Accuracy (5-fold CV) | – | **0.899** | 0.854 |

McNemar's test gives p ≈ 7.4 × 10⁻¹⁴, so the difference between the two models is statistically significant. Decision Tree performs better because it does not rely on feature independence or distribution assumptions, and it can capture interactions between features.

## How to run

1. Click the **Open in Colab** button above.
2. Select **Runtime → Run all**.

The dataset is loaded directly from this repository, so no file upload is needed.

## Repository contents

| File | Description |
|---|---|
| `Project_AI_VideoGame_Hit.ipynb` | Full notebook: EDA, preprocessing, training, tuning, and evaluation |
| `Video_Games_Sales_as_at_22_Dec_2016.csv` | Dataset |
