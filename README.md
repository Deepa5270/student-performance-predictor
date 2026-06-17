# 🎓 Student Performance Predictor

An end-to-end Machine Learning web application that predicts a student's **math score** based on various demographic and academic factors. Built with Python, Flask, and CatBoost — deployed on **AWS Elastic Beanstalk** with a CI/CD pipeline using GitHub Actions.

---

## 📌 Problem Statement

Student performance can be influenced by many factors beyond just studying. This project aims to predict a student's math score using inputs like gender, parental education level, lunch type, and test preparation course — helping educators identify students who may need additional support.

---

## 🚀 Live Demo

> Deployed on AWS Elastic Beanstalk via GitHub Actions CI/CD pipeline.

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Language | Python 3.x |
| Web Framework | Flask |
| ML Model | CatBoost, Scikit-learn |
| Data Processing | Pandas, NumPy |
| Deployment | AWS Elastic Beanstalk |
| CI/CD | GitHub Actions |
| Frontend | HTML, CSS (Jinja2 Templates) |

---

## 📂 Project Structure

```
mlprojects/
│
├── .ebextensions/          # AWS Elastic Beanstalk config
├── .github/workflows/      # GitHub Actions CI/CD pipeline
├── artifacts/              # Saved model and preprocessor files
├── catboost_info/          # CatBoost training logs
├── notebook/               # EDA and model training notebooks
├── src/                    # Source code
│   ├── components/         # Data ingestion, transformation, model trainer
│   ├── pipeline/           # Training and prediction pipelines
│   ├── exception.py        # Custom exception handling
│   ├── logger.py           # Logging setup
│   └── utils.py            # Utility functions
├── templates/              # HTML templates (index, home)
├── app.py                  # Flask application entry point
├── requirements.txt        # Python dependencies
├── setup.py                # Package setup
└── README.md
```

---

## 🔍 Features Used for Prediction

| Feature | Description |
|---|---|
| Gender | Student's gender (male / female) |
| Race/Ethnicity | Group A–E |
| Parental Level of Education | e.g., bachelor's degree, some college |
| Lunch | Standard or free/reduced |
| Test Preparation Course | Completed or none |
| Reading Score | Score out of 100 |
| Writing Score | Score out of 100 |

**Target:** Math Score (regression)

---

## ⚙️ How to Run Locally

### 1. Clone the repository
```bash
git clone https://github.com/Deepa5270/mlprojects.git
cd mlprojects
```

### 2. Create a virtual environment
```bash
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Run the Flask app
```bash
python app.py
```

### 5. Open in browser
```
http://localhost:5000
```

---

## 🧪 Model Training

Training notebooks are available in the `notebook/` folder. The pipeline includes:

- **Data Ingestion** — loads and splits the dataset
- **Data Transformation** — handles encoding and scaling via `ColumnTransformer`
- **Model Training** — trains and evaluates multiple regressors, saves the best model

To retrain the model:
```bash
python src/pipeline/train_pipeline.py
```

---

## 🚢 Deployment (AWS Elastic Beanstalk)

The app is automatically deployed to AWS EB on every push to the `main` branch using GitHub Actions.

**CI/CD Flow:**
1. Push to `main`
2. GitHub Actions triggers the workflow
3. App is packaged and deployed to AWS Elastic Beanstalk

Configuration is in `.ebextensions/` and `.github/workflows/`.

---

## 📊 Model Performance

Multiple regression models were evaluated. The best performing model was selected based on R² score on the test set.

| Model | R² Score |
|---|---|
| CatBoost Regressor | ✅ Best |
| Random Forest | — |
| Linear Regression | — |

*(Update this table with actual scores after training)*

---

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

---

## 🙋‍♀️ Author

**Deepa** — [@Deepa5270](https://github.com/Deepa5270)

---

> ⭐ If you found this project helpful, please give it a star!
