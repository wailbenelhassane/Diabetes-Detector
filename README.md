# Diabetes Prediction System

## 📖 Overview
This project, developed in **Google Colab**, implements a machine learning-based system to predict diabetes using the **PIMA Indians Diabetes Dataset**. The system evaluates multiple models, including **Support Vector Machines (SVM)**, **Logistic Regression**, **Random Forest**, and **Gradient Boosting**, to select the best-performing model for predictions.  
It includes data preprocessing, model training, evaluation, and a predictive function that provides detailed outputs such as **prediction confidence** and **feature contributions**.

---

## 📊 Dataset
The **PIMA Indians Diabetes Dataset** contains medical data from female patients of Pima Indian heritage, with the goal of predicting diabetes. The dataset includes the following features:

- **Pregnancies**: Number of pregnancies.
- **Glucose**: Blood glucose level.
- **BloodPressure**: Blood pressure (mmHg).
- **SkinThickness**: Skin thickness (mm).
- **Insulin**: Insulin level (mu U/ml).
- **BMI**: Body Mass Index.
- **DiabetesPedigreeFunction**: Diabetes pedigree function (genetic heritage).
- **Age**: Age in years.
- **Outcome**: Result (0 = Non-diabetic, 1 = Diabetic).

The dataset is loaded from a CSV file (`dataset.csv`) and preprocessed to handle invalid zero values by replacing them with median values for relevant features.

---

## ⚙️ Features

### 📌 Data Preprocessing
- Handles missing or invalid zero values in **Glucose**, **BloodPressure**, **SkinThickness**, **Insulin**, and **BMI** by replacing them with median values.
- Standardizes features using `StandardScaler` for consistent model input.

### 📌 Model Training and Evaluation
- Trains and evaluates multiple models: **SVM**, **Logistic Regression**, **Random Forest**, and **Gradient Boosting**.
- Uses metrics like **accuracy**, **classification report**, **confusion matrix**, and **cross-validation scores** to assess performance.
- Selects the best model based on test accuracy.

### 📌 Predictive System
- A `predict_diabetes` function that:
  - Takes user input, preprocesses it, and predicts whether the patient is diabetic or non-diabetic.
  - Provides **prediction confidence** (for models with `predict_proba`) and **feature contributions** (for tree-based models like Random Forest and Gradient Boosting).
  - Includes input validation to ensure data integrity.

### 📌 Visualization
- Uses **Matplotlib** and **Seaborn** for exploratory data analysis (e.g., **correlation heatmaps**, **distribution plots**).
- Displays **confusion matrices** for model evaluation.

---

## 📦 Prerequisites

To run this project, ensure you have the following dependencies installed:

- **Python 3.x**
- Libraries:
  - `numpy`
  - `pandas`
  - `scikit-learn`
  - `matplotlib`
  - `seaborn`

Install them using pip:

```bash
pip install numpy pandas scikit-learn matplotlib seaborn
```

Additionally, you need the **PIMA Indians Diabetes Dataset (`dataset.csv`)** in the project directory or uploaded to Google Colab.

---

## 🚀 Usage

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/diabetes-prediction.git
cd diabetes-prediction
```

### 2️⃣ Open in Google Colab
- Upload the `Diabetes_Detector.ipynb` notebook to Google Colab.
- Upload the `dataset.csv` file to the Colab environment or adjust the file path in the notebook to point to the dataset location.

### 3️⃣ Run the Notebook
- Execute the cells in the notebook sequentially to:
  - Load and preprocess the dataset.
  - Train and evaluate models.
  - Use the predictive system with example input data.

Example prediction with input data:

```python
input_data = (1, 89, 66, 23, 94, 28.1, 0.167, 21)
```

This will output the prediction result, confidence scores, and feature contributions (if applicable).

### 4️⃣ Modify Input Data
To test new predictions, modify the `input_data` tuple in the notebook with values for the eight features:

- Pregnancies  
- Glucose  
- BloodPressure  
- SkinThickness  
- Insulin  
- BMI  
- DiabetesPedigreeFunction  
- Age  

Ensure input values are non-negative numbers and match the expected format.

---

## 📁 Project Structure

```
.
├── Diabetes_Detector.ipynb    # Main notebook for data preprocessing, model training, evaluation, and prediction
├── dataset.csv                # PIMA Indians Diabetes Dataset (not included, source externally)
└── README.md                  # Project overview and instructions
```

---

## 📊 Example Output

For the example input `(1, 89, 66, 23, 94, 28.1, 0.167, 21)` with **Random Forest** as the best model, the output might look like:

```
Selected model for prediction: Random Forest (Test Accuracy: 0.7792)

Prediction Results:
Input Data: (1, 89, 66, 23, 94, 28.1, 0.167, 21)
Result: Non-Diabetic
Confidence: Non-Diabetic: 0.9600, Diabetic: 0.0400

Feature Contributions:
                 Feature  Contribution
                 Glucose     -0.298694
                     Age     -0.118170
DiabetesPedigreeFunction     -0.117595
                     BMI     -0.103211
             Pregnancies     -0.068785
                 Insulin     -0.050660
           SkinThickness     -0.047925
           BloodPressure     -0.041810
```

---

## 📝 Notes

- The dataset must be available in the correct path (`/content/dataset.csv` in Colab) or updated in the notebook.
- The notebook assumes the dataset has no missing values other than invalid zeros, which are handled during preprocessing.
- The predictive system is designed for the **PIMA dataset's specific features** and may not generalize to other datasets without modification.
- For deployment outside Colab, you may need to save the trained model and scaler (e.g., using `joblib`) and adapt the code for a different environment.

---
