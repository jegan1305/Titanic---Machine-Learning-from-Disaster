# 🚢 Titanic Survival Prediction

A Machine Learning project that predicts whether a passenger survived the Titanic disaster using passenger information such as age, gender, passenger class, fare, family size, and embarkation port.

The project follows an end-to-end Machine Learning workflow including data extraction, data exploration, feature engineering, preprocessing, model training, evaluation, and prediction.

## 📌 Project Overview

The goal of this project is to build a Machine Learning model capable of predicting passenger survival based on the available Titanic passenger data.

A **Random Forest Classifier** is used as the primary prediction model.

### Workflow

```text
Dataset
   ↓
Data Loading
   ↓
Data Exploration
   ↓
Feature Engineering
   ↓
Data Preprocessing
   ↓
Train / Validation Split
   ↓
Random Forest Model
   ↓
Model Evaluation
   ↓
Final Training
   ↓
Test Prediction
   ↓
submission.csv
```

## 📂 Dataset

The project uses the classic Titanic dataset containing:

* `train.csv` — Training dataset containing passenger information and survival labels
* `test.csv` — Test dataset used for final predictions
* `gender_submission.csv` — Sample submission format

### Important Features

| Feature    | Description                       |
| ---------- | --------------------------------- |
| `Pclass`   | Passenger class                   |
| `Sex`      | Passenger gender                  |
| `Age`      | Passenger age                     |
| `SibSp`    | Number of siblings/spouses aboard |
| `Parch`    | Number of parents/children aboard |
| `Fare`     | Passenger fare                    |
| `Embarked` | Port of embarkation               |
| `Name`     | Passenger name                    |

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Jupyter Notebook
* Random Forest
* Machine Learning
* Data Preprocessing
* Feature Engineering

## ⚙️ Feature Engineering

Several additional features were created to improve the model.

### Title

Passenger titles were extracted from the `Name` column.

Examples:

```text
Mr
Miss
Mrs
Master
Rare
```

Rare titles were grouped into a common `Rare` category.

### FamilySize

Family size was calculated using:

```text
FamilySize = SibSp + Parch + 1
```

### IsAlone

A binary feature was created to identify whether a passenger was travelling alone.

```text
IsAlone = 1 → Passenger travelling alone
IsAlone = 0 → Passenger travelling with family
```

## 🔄 Data Preprocessing

The project uses Scikit-learn pipelines for preprocessing.

### Numerical Features

Missing numerical values are handled using **median imputation**.

Numerical features include:

```text
Age
SibSp
Parch
Fare
FamilySize
IsAlone
```

### Categorical Features

Missing categorical values are filled using the most frequent value.

Categorical features are then converted using **One-Hot Encoding**.

Categorical features include:

```text
Pclass
Sex
Embarked
Title
```

## 🤖 Machine Learning Model

The primary model used is:

### Random Forest Classifier

The model uses:

```text
n_estimators = 500
max_depth = 6
min_samples_split = 4
min_samples_leaf = 2
random_state = 42
```

A Scikit-learn `Pipeline` combines preprocessing and model training into a single workflow.

## 📊 Model Evaluation

The dataset is divided into training and validation sets.

The model is evaluated using:

* Accuracy
* Classification Report
* Confusion Matrix

Example:

```python
accuracy_score(y_valid, y_pred)
```

The classification report provides:

* Precision
* Recall
* F1-score
* Support

## 🔮 Final Prediction

After evaluating the model, it is retrained using the complete training dataset.

Predictions are then generated for `test.csv`.

The final predictions are saved as:

```text
submission.csv
```

The submission file contains:

```text
PassengerId
Survived
```

Example:

```text
PassengerId,Survived
892,0
893,1
894,0
895,1
```

## 📁 Project Structure

```text
Titanic-Survival-Prediction/
│
├── data/
│   ├── train.csv
│   ├── test.csv
│   └── gender_submission.csv
│
├── notebooks/
│   └── Titanic_Analysis.ipynb
│
├── submission.csv
│
├── requirements.txt
│
└── README.md
```

## 🚀 How to Run

### 1. Clone the repository

```bash
git clone <your-repository-url>
```

### 2. Navigate to the project

```bash
cd Titanic-Survival-Prediction
```

### 3. Install dependencies

```bash
pip install pandas numpy scikit-learn jupyter
```

Or:

```bash
pip install -r requirements.txt
```

### 4. Run the notebook

```bash
jupyter notebook
```

Open the Titanic analysis notebook and run the cells sequentially.

## 📈 Future Improvements

Possible improvements for this project:

* Compare Random Forest with Logistic Regression and Decision Tree
* Perform hyperparameter tuning
* Add more feature engineering
* Perform detailed Exploratory Data Analysis
* Add feature importance visualization
* Build a Streamlit prediction interface
* Deploy the model as a web application

## 👨‍💻 Author

**Jegan Vennila**

B.Tech Artificial Intelligence & Data Science

---

⭐ If you found this project useful, consider giving the repository a star!
