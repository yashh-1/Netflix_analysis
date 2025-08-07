 ## 📺 Netflix Data: Cleaning, Analysis, and Visualization

This project explores Netflix's content data from 1925 to 2021 to uncover insights about content trends, duration, countries, genres, and more. It includes data cleaning, exploratory data analysis (EDA), feature engineering, and a machine learning model to predict content type (Movie or TV Show).

---

##  Dataset Overview

- **Platform**: Netflix  
- **Data Range**: 1925 – 2021  
- **Source**: Public Netflix dataset (cleaned version in Excel format)  
- **Total Records**: 8,790  
- **Key Columns**:
  - `type`, `title`, `director`, `country`, `date_added`, `release_year`
  - `rating`, `duration`, `listed_in`

---

## Project Workflow

###  Step 1: Data Cleaning
- Removed nulls in critical fields (`title`, `release_year`)
- Filled missing `country`, `director`, `rating` with `"Unknown"`
- Converted `date_added` to datetime
- Extracted:
  - `duration_num`, `duration_unit` from `duration`
  - Removed duplicates

###  Step 2: Exploratory Data Analysis (EDA)
- Countplot of **Movies vs TV Shows**
- Year-wise content addition trend
- Top 10 **genres** and **countries** visualized
- Word cloud of content genres
- Duration and season trends

###  Step 3: Feature Engineering
- Created:
  - `genre_count` – number of genres per title
  - `duration_min` – for movies
  - `season_count` – for TV shows
  - `type_encoded`, `rating_encoded` – for ML
  - `month_added`, `day_added` – from `date_added`

###  Step 4: Machine Learning
- **Model**: Random Forest Classifier  
- **Target**: `type` → Movie or TV Show  
- **Features**:
  - `release_year`, `genre_count`, `duration_min`, `season_count`, `rating_encoded`, `month_added`, `day_added`
- **Evaluation**:
  - Confusion Matrix  
  - Classification Report  
  - Accuracy Score

###  Step 5: Feature Importance
- Visualized importance of features using barplot  
- **Top Features**:
  - `duration_min`, `season_count`, `release_year`, `rating_encoded`

###  Step 6: Save Model
- Trained model saved as: `netflix_content_type_model.pkl` using `joblib`

---

##  Key Insights

- **Movies** dominate Netflix’s content, but **TV Shows** are growing in number.
- Most Netflix content originates from **USA**, **India**, and **UK**.
- The peak years for new additions were **2019–2020**, likely due to COVID-19.
- **Top genres**: Dramas, Comedies, International content.
- **Random Forest Model** performs well in predicting content type with duration and release year as key indicators.

---

## Tools & Libraries

- Python 
- Pandas, NumPy  
- Matplotlib, Seaborn  
- Scikit-learn  
- Joblib  
- Jupyter Notebook

---
