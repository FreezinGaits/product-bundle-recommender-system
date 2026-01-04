# Product Bundle Recommender System  
![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![Pandas](https://img.shields.io/badge/Pandas-2.x-brightgreen)
![NumPy](https://img.shields.io/badge/NumPy-1.x-blue)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.x-orange)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)
![Status](https://img.shields.io/badge/Status-Completed-success)

**A production-ready, explainable product bundle recommendation system built end-to-end on the UCI Online Retail dataset.**

## Why This Project Stands Out

I built this project from scratch to demonstrate **real-world MLOps thinking** and **production-grade machine learning engineering** — exactly the skills recruiters look for in mid-to-senior Data Scientist / ML Engineer roles.

This is **not** a quick Kaggle notebook with a high score. It's a **complete, reproducible pipeline** designed with scalability, explainability, and business impact in mind.

## Project Overview

Using the classic **Online Retail** transactional dataset (~530k rows), I built a **co-purchase-based bundle recommender** that suggests complementary products (e.g., "Customers who bought this also bought...").

Key highlights:
- Fully documented, modular notebook pipeline (01 → 07)
- Clean separation of concerns: exploration → cleaning → feature engineering → modeling → evaluation → inference → insights
- Rule-based, interpretable model (no black-box deep learning)
- Time-aware co-occurrence scoring to capture evolving trends
- Popularity normalization to avoid trivial recommendations
- Cold-start handling via global popularity fallback
- Rigorous offline evaluation with time-based train/test split (no data leakage)
- Clear business-oriented insights dashboard

## Pipeline Structure

| Notebook | Purpose | Key Skills Demonstrated |
|--------|--------------------------------|------------------------|
| `01_data_understanding.ipynb` | Exploratory Data Analysis | Data intuition, visualization, long-tail analysis |
| `02_data_cleaning.ipynb` | Robust cleaning & validation | Handling cancellations, missing values, data integrity |
| `03_feature_engineering.ipynb` | Basket construction, time-weighted co-occurrence | Scalable pair counting, efficient feature design |
| `04_bundle_model.ipynb` | Recommendation logic & scoring | Algorithm design, dictionary lookups for O(1) inference |
| `05_evaluation.ipynb` | Time-split offline evaluation (Hit@K) | Proper validation, baseline comparison |
| `06_prediction.ipynb` | Inference demo with human-readable output | Production-like API simulation |
| `07_insights.ipynb` | Business insights & visualizations | Translating ML into actionable retail strategy |

## Technical & Engineering Highlights

- **Production-minded design**: All artifacts saved as Parquet for fast loading in production
- **Efficient memory usage**: Dictionary-based lookup structures for sub-millisecond recommendations
- **Time-aware modeling**: Recent co-purchases weighted higher using exponential decay
- **Bias mitigation**: Popularity normalization via `log(1 + popularity)` to surface meaningful bundles
- **Cold-start strategy**: Graceful fallback to top global products
- **Proper evaluation**: 80/20 temporal split → Hit@5 = **76.7%** vs baseline **47.1%** (+63% relative lift)
- **Explainable by design**: Every recommendation traceable to co-purchase history

## Results

| Metric       | Model   | Popularity Baseline | Relative Lift |
|------------|---------|---------------------|---------------|
| Hit@3      | **69.1%** | 36.3%               | +90%          |
| Hit@5      | **76.7%** | 47.1%               | +63%          |
| Hit@10     | **85.4%** | 67.9%               | +26%          |

The model significantly outperforms a simple "recommend most popular" baseline — proving that co-purchase patterns add real value.

## Example Recommendation

**Input Product**: `85123A` – *WHITE HANGING HEART T-LIGHT HOLDER* (one of the bestsellers)

**Top 5 Recommended Bundles**:
1. DOTCOM POSTAGE
2. HAND OVER THE CHOCOLATE SIGN
3. SMALL HANGING IVORY/RED WOOD BIRD
4. LADIES & GENTLEMEN METAL SIGN
5. SET OF 6 3D KIT CARDS FOR KIDS

These are **non-trivial**, thematic complements — exactly what merchandising teams want.

## What This Project Shows About Me

- I think **end-to-end**: from raw CSV to business insights
- I prioritize **reproducibility, clarity, and documentation**
- I design systems with **production deployment in mind** (fast inference, no heavy dependencies)
- I validate rigorously with **temporal splits** and strong baselines
- I can translate technical work into **business value** (insights notebook)
- I write clean, modular, well-commented code

## Future Improvements (Already Planned)

- Deploy as FastAPI service with caching
- Add user-based personalization layer
- A/B test integration
- Support for bundle size >2 (triplets, etc.)
- Confidence scoring and filtering

## Try It Yourself

1. Clone the repo
2. Install dependencies: `pip install pandas numpy matplotlib seaborn`
3. Open `06_prediction.ipynb` → pick any StockCode → see live recommendations!

---

## 👨‍💻 Author

Gautam Sharma  
Computer Science Engineering (B.Tech)  
Focused on Machine Learning & MLOps 

This project was built to reflect real-world ML engineering practices, not just model training.
---
⭐ This repository demonstrates a complete, production-oriented machine learning pipeline — from raw transactional data to a fast, explainable, and evaluated product bundle recommender system — mirroring how real-world recommendation systems are designed, validated, and prepared for deployment.
*Built with ❤️ and attention to detail — January 2026*