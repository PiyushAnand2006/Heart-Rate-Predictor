# ❤️ Heart Stroke Prediction

A machine learning mini project that predicts the risk of heart disease based on clinical parameters. The project includes an end-to-end workflow: data exploration & cleaning, model training with multiple algorithms, and a **Streamlit** web app for interactive predictions.

## 📁 Project Structure

```
heart-stroke-prediction/
├── dataset/
│   └── heart.csv                  # Dataset (918 records)
├── notebook/
│   └── heart.ipynb                # EDA, preprocessing & model training
├── models/
│   ├── app.py                     # Streamlit web application
│   ├── Logistic_Regression_heart.pkl  # Trained Logistic Regression model
│   ├── scaler.pkl                 # StandardScaler used in training
│   └── columns.pkl                # Expected feature columns (after encoding)
```

## 📊 Dataset

The dataset (`heart.csv`) contains **918 records** with 12 columns:

| Feature | Description |
|---|---|
| `Age` | Age of the patient (years) |
| `Sex` | M / F |
| `ChestPainType` | ATA, NAP, TA, ASY |
| `RestingBP` | Resting blood pressure (mm Hg) |
| `Cholesterol` | Serum cholesterol (mg/dL) |
| `FastingBS` | Fasting blood sugar > 120 mg/dL (1 = true; 0 = false) |
| `RestingECG` | Normal, ST, LVH |
| `MaxHR` | Maximum heart rate achieved |
| `ExerciseAngina` | Exercise-induced angina (Y / N) |
| `Oldpeak` | ST depression induced by exercise |
| `ST_Slope` | Up, Flat, Down |
| `HeartDisease` | Target variable (1 = heart disease, 0 = normal) |

## 🔍 Workflow (notebook/heart.ipynb)

1. **Exploratory Data Analysis** – distributions, count plots, box plots, violin plots, and a correlation heatmap.
2. **Data Cleaning**
   - Replaced invalid `0` values in `Cholesterol` and `RestingBP` with their non-zero column means.
3. **Preprocessing**
   - One-hot encoding of categorical features (`pd.get_dummies`).
   - Feature scaling with `StandardScaler` on numeric columns.
4. **Model Training & Comparison**

   | Model | Metric Tracked |
   |---|---|
   | Logistic Regression ✅ (selected) | Accuracy, F1 Score |
   | K-Nearest Neighbors | Accuracy, F1 Score |
   | Naive Bayes | Accuracy, F1 Score |
   | Decision Tree | Accuracy, F1 Score |
   | SVM (RBF Kernel) | Accuracy, F1 Score |

5. **Model Persistence** – best model, scaler, and column list saved as `.pkl` files using `joblib`.

## 🚀 Getting Started

### Prerequisites

- Python 3.11+ (developed with Jupyter Notebook for the training notebook)

### Installation

```bash
pip install -r requirements.txt
```

### Run the Streamlit App

```bash
cd models
streamlit run app.py
```

Then open the app in your browser, enter patient details, and click **Predict** to get:

- ⚠️ High Risk of Heart Disease
- ✅ Low Risk of Heart Disease

## 🧠 How the App Works

1. User provides inputs via sliders/dropdowns.
2. Inputs are converted into a one-hot encoded DataFrame matching the training columns.
3. Values are scaled with the saved `StandardScaler`.
4. The Logistic Regression model outputs the prediction.

> **Note:** This is an educational project and should not be used for actual medical diagnosis.

## 🛠️ Tech Stack

- Python 🐍 (3.11+)
- Jupyter Notebook – training & EDA
- Pandas, NumPy – data manipulation
- Seaborn, Matplotlib – visualization
- Scikit-learn – ML models & preprocessing
- Joblib – model serialization
- Streamlit – web app UI

## 📜 License

This project is for learning purposes. Feel free to fork and experiment!
