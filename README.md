# 🌍 Tourism Experience Analytics

### Classification • Rating Prediction • Recommendation System

An end-to-end **Data Analytics and Machine Learning project** that analyzes tourist behavior, predicts attraction ratings, classifies visitor modes, and generates personalized attraction recommendations using historical tourism data.

---

## 📌 Project Overview

**Tourism Experience Analytics** is designed to understand tourist behavior and improve travel experiences using **Data Analytics, Machine Learning, and Recommendation Systems**.

The project works with tourism data containing information about:

* 👤 Users
* 🏙️ Cities
* 🌎 Countries
* 🌍 Regions
* 🌐 Continents
* 🏛️ Attractions
* ⭐ Ratings
* ✈️ Visit Modes
* 📅 Visit Year & Month

The system performs three major Machine Learning tasks:

1. 📈 **Rating Prediction** – Predicts the rating a user may give to an attraction.
2. 🎯 **Visit Mode Classification** – Predicts whether the visit is Solo, Couples, Family, Friends, or Business.
3. ⭐ **Personalized Recommendation** – Recommends attractions based on similar users, ratings, and popularity.

The final project also includes an interactive **Gradio interface** for exploring the results and generating personalized recommendations.

---

## 🎯 Problem Statement

Tourism platforms generate large amounts of information about tourist visits, preferences, ratings, demographics, and attractions. However, this data can be difficult to utilize effectively for understanding user behavior and providing personalized experiences.

This project addresses the problem by applying **Data Analytics and Machine Learning** to:

* Understand tourism trends and user behavior
* Predict attraction ratings
* Classify users according to their visit mode
* Recommend attractions based on user preferences
* Generate useful insights for tourism businesses

---

## 🚀 Key Features

### 📊 1. Data Analysis

* Data cleaning and preprocessing
* Missing-value and duplicate handling
* Data validation
* Feature engineering
* Exploratory Data Analysis
* Tourism trend analysis
* Rating distribution analysis
* Visit-mode analysis
* Popular attraction analysis

### 📈 2. Rating Prediction

Regression models are used to predict attraction ratings.

**Models Used:**

* Random Forest Regressor
* XGBoost Regressor
* CatBoost Regressor

**Evaluation Metrics:**

* MAE
* RMSE
* R² Score

The implemented experiments selected **Random Forest** as the best regression model with:

| Metric |  Score |
| ------ | -----: |
| MAE    | 0.7038 |
| RMSE   | 0.9001 |
| R²     | 0.1473 |

---

### 🎯 3. Visit Mode Classification

The classification model predicts the visitor's likely travel mode.

Possible categories include:

* Solo
* Couples
* Family
* Friends
* Business

**Models Used:**

* Random Forest Classifier
* XGBoost Classifier
* CatBoost Classifier

**Evaluation Metrics:**

* Accuracy
* Precision
* Recall
* F1 Score

The implemented experiment reported **XGBoost** as the selected classification model with:

| Metric    |  Score |
| --------- | -----: |
| Accuracy  | 1.0000 |
| Precision | 1.0000 |
| Recall    | 1.0000 |
| F1 Score  | 1.0000 |

> **Note:** These metrics are from the project's implemented train/test experiment and should be interpreted in the context of the selected features and data split.

---

### ⭐ 4. Personalized Recommendation System

The recommendation engine uses **KNN-based collaborative filtering** with a sparse user-item interaction matrix.

The recommendation score combines:

* 🤝 Collaborative similarity — **60%**
* ⭐ Attraction rating — **25%**
* 🔥 Attraction popularity — **15%**

### Hybrid Score

```text
Hybrid Score =
0.60 × Collaborative Score
+ 0.25 × Rating Score
+ 0.15 × Popularity Score
```

## The system removes attractions that the user has already visited and returns a ranked list of recommended attractions.

## 📂 Dataset

The project uses a Tourism Dataset consisting of multiple Excel files:

```text
Tourism Dataset/
│
├── Transaction.xlsx
├── User.xlsx
├── City.xlsx
├── Country.xlsx
├── Region.xlsx
├── Continent.xlsx
├── Mode.xlsx
├── Type.xlsx
├── Item.xlsx
│
└── Additional_Data_for_Attraction_Sites/
    └── Updated_Item.xlsx
```

The implemented dataset contains:

| Data             |  Count |
| ---------------- | -----: |
| Transactions     | 52,930 |
| Users            | 33,530 |
| Attractions      |     30 |
| Cities           |  5,545 |
| Countries        |    165 |
| Regions          |     22 |
| Continents       |      6 |
| Visit Modes      |      6 |
| Attraction Types |     17 |

---

## 🛠️ Tech Stack

### Programming Language

* Python

### Data Analysis

* Pandas
* NumPy

### Data Visualization

* Matplotlib
* Seaborn

### Machine Learning

* Scikit-learn
* XGBoost
* CatBoost

### Recommendation System

* KNN
* Cosine Similarity
* Sparse User-Item Matrix

### Interface

* Gradio

### Model & Data Storage

* Joblib
* CSV
* Excel

---

## 🔄 Project Workflow

```text
              Tourism Dataset
                    │
                    ▼
          Data Cleaning & Validation
                    │
                    ▼
          Data Preprocessing
                    │
                    ▼
           Feature Engineering
                    │
                    ▼
          Exploratory Data Analysis
                    │
                    ▼
             Data Visualization
                    │
          ┌─────────┼──────────┐
          ▼         ▼          ▼
      Regression  Classification  Recommendation
          │         │          │
          ▼         ▼          ▼
     Rating      Visit Mode   KNN + Hybrid
    Prediction   Prediction   Recommendations
          │         │          │
          └─────────┼──────────┘
                    ▼
             Model Evaluation
                    │
                    ▼
             Gradio Interface
                    │
                    ▼
       Personalized Tourism Insights
```

---

## 🧹 Data Preprocessing

The project performs several preprocessing steps:

* Removes duplicate transaction records
* Converts numerical columns to appropriate numeric types
* Removes invalid ratings outside the **1–5** range
* Validates visit months between **1–12**
* Merges user, attraction, type, mode, and city information
* Creates additional features
* Optimizes numerical data types to reduce memory usage

---

## ⚙️ Feature Engineering

Several useful features were created from historical tourism behavior.

### User-Level Features

* User Average Rating
* User Visit Count
* User Attraction Count

### Attraction-Level Features

* Attraction Average Rating
* Attraction Visit Count
* Attraction User Count

### Time-Based Features

* Visit Quarter
* Peak Season Indicator

The final engineered dataset contains **28 features/columns** in the implemented workflow.

---

## 📊 Exploratory Data Analysis

The project analyzes:

* Tourist rating distribution
* Visit-mode distribution
* Most visited attractions
* User demographics
* Tourism patterns
* Attraction popularity

### Visit Mode Distribution

| Visit Mode | Visits |
| ---------- | -----: |
| Couples    | 21,620 |
| Family     | 15,217 |
| Friends    | 10,945 |
| Solo       |  4,525 |
| Business   |    623 |

---

## 💾 Generated Project Files

The project saves the trained models and processed dataset using Joblib and CSV:

```text
best_rating_model.pkl
best_visit_mode_model.pkl
tourism_knn_recommender.pkl
user_to_index.pkl
attraction_ids.pkl
tourism_cleaned_dataset.csv
```

---

## 🖥️ Gradio Interface

The project includes an interactive Gradio interface with different sections:

* 📊 Dataset Overview
* 📈 Rating Prediction
* 🎯 Visit Mode Classification
* ⭐ Recommendation System
* 📋 Project Summary

Users can enter a **User ID** and select the number of recommendations they want. The system then generates personalized attraction recommendations.

---

## 📌 Example Recommendation Output

For a sample user, the recommendation engine generated attractions such as:

| Rank | Attraction       | Type            | Average Rating |
| ---: | ---------------- | --------------- | -------------: |
|    1 | Tanah Lot Temple | Religious Sites |           4.19 |
|    2 | Waterbom Bali    | Water Parks     |           4.65 |
|    3 | Uluwatu Temple   | Religious Sites |           4.22 |

---

## 📁 Suggested Repository Structure

```text
Tourism-Experience-Analytics/
│
├── README.md
├── Tourism_Experience_Analytics.ipynb
│
├── data/
│   └── README.md
│
├── models/
│   ├── best_rating_model.pkl
│   ├── best_visit_mode_model.pkl
│   ├── tourism_knn_recommender.pkl
│   ├── user_to_index.pkl
│   └── attraction_ids.pkl
│
├── outputs/
│   └── tourism_cleaned_dataset.csv
│
├── app/
│   └── app.py
│
└── requirements.txt
```

---

## ▶️ How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/Tourism-Experience-Analytics.git
cd Tourism-Experience-Analytics
```

### 2. Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost catboost scipy joblib gradio openpyxl
```

### 3. Run the Notebook

Open:

```text
Tourism_Experience_Analytics.ipynb
```

You can run it using **Google Colab** or **Jupyter Notebook**.

### 4. Run the Application

If the Gradio application is saved separately:

```bash
python app.py
```

The interface will provide access to the project's tourism analytics, model information, and recommendation functionality.

---

## 📈 Final Results

```text
================ TOURISM EXPERIENCE ANALYTICS ================

Dataset
├── Transactions: 52,930
├── Users:        33,530
├── Attractions: 30
└── Cities:       5,545

Regression
├── Best Model: Random Forest
├── MAE:  0.7038
├── RMSE: 0.9001
└── R²:   0.1473

Classification
├── Best Model: XGBoost
├── Accuracy:  1.0000
├── Precision: 1.0000
├── Recall:    1.0000
└── F1 Score:  1.0000

Recommendation
├── Algorithm: KNN Collaborative Filtering
└── Method: Hybrid Collaborative + Rating + Popularity
```

---

## 💡 Business Applications

This project can support tourism businesses in:

* Personalized attraction recommendations
* Understanding tourist preferences
* Customer segmentation
* Targeted marketing
* Attraction popularity analysis
* Improving customer engagement
* Supporting tourism decision-making

---

## 🔮 Future Improvements

Potential future improvements include:

* Deploying the application permanently
* Adding more tourism datasets
* Incorporating real-time travel information
* Adding location-based recommendations
* Improving cold-start recommendations for new users
* Adding more advanced recommendation algorithms
* Building a web/mobile version
* Adding interactive tourism dashboards

---

## 👩‍💻 Author

**Shaily Yadav**

B.Tech CSE — Artificial Intelligence & Machine Learning

**Interests:** Data Analytics • Machine Learning • AI • Data Visualization

---

## ⭐ Project Highlights

```text
✔ End-to-End Data Analytics Project
✔ 52K+ Tourism Transactions
✔ 33K+ Users
✔ Machine Learning Classification
✔ Machine Learning Regression
✔ KNN Recommendation System
✔ Hybrid Recommendation Score
✔ Feature Engineering
✔ Exploratory Data Analysis
✔ Interactive Gradio Interface


This project is created for **educational and portfolio purposes**.
