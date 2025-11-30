# NCAA to NBA Draft Prediction

Predicting NBA draft outcomes from college basketball statistics using machine learning.

## 🏀 Project Overview

Built a machine learning pipeline to predict whether NCAA basketball players will be drafted to the NBA based on their final season statistics. Analyzed 3,375 prospects from 2013-2017 seasons, achieving 53% recall on draft picks while maintaining 42% precision.

##  Key Results

- **Best Model:** XGBoost with class-weighted training
- **Performance:** 93% accuracy, 53% recall on drafted players
- **Key Finding:** Games played and started were stronger predictors (30% combined feature importance) than pure scoring statistics

##  Technologies Used

- **Data Extraction:** SQL (Google BigQuery)
- **Data Processing:** Python (pandas, numpy)
- **Machine Learning:** scikit-learn, XGBoost
- **Environment:** Jupyter Notebook (Google Colab)

## 📁 Project Structure
```
├── NBA_Draft_Prediction.ipynb    # Main analysis notebook
├── ncaa_data_v1.csv               # NCAA player statistics (2013-2017)
├── nba_draft_data.csv             # NBA draft picks data
└── README.md                       # Project documentation
```

##  Methodology

### 1. Data Collection
- Extracted NCAA player statistics from BigQuery public dataset
- Aggregated game-level stats into season averages
- Filtered to players with 20+ games for statistical reliability

### 2. Data Cleaning & Merging
- Aligned NCAA season years with NBA draft years (+1 offset)
- Filtered to realistic draft prospects (8+ PPG)
- Created binary target variable (drafted vs undrafted)

### 3. Model Training
Tested three algorithms:
- Logistic Regression (baseline)
- Random Forest
- XGBoost (selected for balanced performance)

Used class weighting to handle 6/94 class imbalance.

### 4. Evaluation
- 80/20 train/test split with stratification
- Evaluated using precision, recall, and F1-score
- Analyzed feature importance for insights

## 📈 Results Summary

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| Logistic Regression | 81% | 20% | 77% | 0.32 |
| Random Forest | 94% | 48% | 37% | 0.42 |
| **XGBoost** | **93%** | **42%** | **53%** | **0.47** |

**Top Predictive Features:**
1. Games Played (15.4%)
2. Games Started (15.1%)
3. Average Points (11.3%)
4. Average Rebounds (7.8%)
5. Two-Pointers Made (6.5%)

##  Key Insights

- **Durability matters:** Games played/started combined for 30% of predictive importance
- **Beyond scoring:** Consistency and opportunity were stronger signals than raw point totals
- **Class balance:** Managed 1:15 imbalance using class weights and appropriate metrics
- **Model selection:** Trade-off between recall (catching draft picks) and precision (avoiding false alarms)

##  Future Improvements

- Add physical measurements (height, wingspan, combine data)
- Incorporate strength of schedule adjustments
- Include advanced metrics (PER, Win Shares, Box Plus/Minus)
- Expand dataset beyond 2013-2017 timeframe
- Hyperparameter tuning with GridSearchCV

##  Skills Demonstrated

- SQL data extraction and aggregation
- Data cleaning and quality validation
- Handling imbalanced datasets
- Feature engineering and selection
- Model training, evaluation, and comparison
- Feature importance interpretation
- Clear technical communication

## 📝 Data Sources

- **NCAA Statistics:** [BigQuery Public Dataset](https://console.cloud.google.com/marketplace/product/ncaa-bb-public/ncaa-basketball)
- **NBA Draft Data:** Kaggle (20 years of NBA draft data)

##  Contact

[Your Name]  
[LinkedIn](https://www.linkedin.com/in/callanwong/) | [Email](mailto:wongcallan@gmail.com)

---

*Built as part of portfolio development for analytics/data science internship applications.*
