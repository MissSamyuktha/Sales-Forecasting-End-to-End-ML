# 🛒 SuperKart Sales Forecasting Project

## 📌 Overview
In this project I designed and deployed an **end-to-end sales forecasting solution** for *SuperKart*, a retail chain operating supermarkets and food marts across tiered cities.  

The goal is to forecast **quarterly sales revenue** for each store, enabling better inventory management, supply chain planning, and regional sales strategies.

---

## 🎯 Business Context
Accurate sales forecasting adds value across an organization:
- Optimizes procurement and inventory management
- Reduces risks in the sales pipeline
- Improves decision-making for territory coverage
- Establishes benchmarks for future trend analysis

---

## 🛠️ Technical Approach
### Data
- Historical sales data with **numerical features** (e.g., product weight, allocated area, MRP)  
- **Categorical features** (e.g., sugar content, product type, store details)

### Models Evaluated
- Linear Regression, Lasso, Ridge, ElasticNet
- SGDRegressor, Support Vector Regression (SVR)
- KNN Regressor
- Decision Tree, Random Forest
- XGBoost Regressor

### Model Selection
- **XGBoost** delivered the best performance (R² ≈ 92.8% on test data).  
- For simplicity and interpretability, **KNN Regressor** was chosen for deployment.
- 
### 🧰 Tech Stack  
Python 3.10, scikit-learn, XGBoost, Flask, Streamlit, Docker, Hugging Face Spaces

### Metrics
- **Root Mean Square Error (RMSE)**
- **R² Score**

### 📊 Results  
- KNN Regressor: R² = 0.90 (test), RMSE ~ 335
- XGBoost Regressor: R² = 0.93 (test), RMSE ~ 286
---

## ⚙️ Deployment
The project is deployed as a **two-tier application** on Hugging Face Spaces:

### Backend (Flask API)
- Preprocessing pipeline (`StandardScaler` + `OneHotEncoder`)
- KNN Regressor model
- Exposes `/predict` endpoint for sales forecasting
- Containerized with **Docker**

### Frontend (Streamlit UI)
- User-friendly form to input product & store details
- Calls backend API and displays forecasted sales
- Deployed separately on Hugging Face Spaces
---

## 🌟 Key Learnings
- Built an end-to-end ML pipeline: preprocessing, training, evaluation, deployment
- Balanced accuracy vs. simplicity for deployment
- Hands-on experience with model serving and UI integration
- Ready to tackle real-world data science projects in industry

## 🔖 Future Improvements
- Deploy XGBoost model for higher accuracy
- Add monitoring & logging for predictions
- Integrate CI/CD for automated builds

# 👩‍💻 Author
**Samyuktha Kalivemula** 
Aspiring Data Scientist | Transitioning into the Data /AI/ML job market | Passionate about solving business problems with ML.

If you’re a recruiter or collaborator interested in data-driven solutions, feel free to reach out or connect with me on LinkedIn!https://www.linkedin.com/in/samyuktha-kalivemula/


## 🚀 How to Run Locally
### Backend
```bash
cd backend
docker build -t superkart-backend .
docker run -p 7860:7860 superkart-backend

### Frontend
cd frontend
docker build -t superkart-frontend .
docker run -p 7860:7860 -e BACKEND_URL=http://localhost:7860 superkart-frontend ```bash

---
