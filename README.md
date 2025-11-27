📌 Project Workflow

1️⃣ Data Preprocessing

✔ Removed unused columns (e.g., customerID)

✔ Fixed missing values in TotalCharges

✔ Converted appropriate features to numerical format

✔ Identified and handled class imbalance

✔ Applied Label Encoding to categorical features

✔ Saved encoders into encoders.pkl for future prediction consistency



2️⃣ Exploratory Data Analysis (EDA)

The notebook includes:

Distribution of numerical features

Boxplots to identify outliers

Countplots for categorical variables

Correlation heatmap

Churn rate analysis

This step helps understand the dataset structure and patterns affecting churn.



3️⃣ Train–Test Split

The dataset is split into:

80% Training data

20% Testing data

Random state fixed for reproducibility.



4️⃣ Handling Class Imbalance (SMOTE)

The original dataset contains significantly fewer churned customers.

We apply:

SMOTE()

This creates synthetic minority samples and improves training balance.



5️⃣ Model Training

Three machine-learning models are trained with default hyperparameters:

Decision Tree

Random Forest

XGBoost Classifier

Cross-validation (5-fold) is used for comparison.

🏆 Best Performing Model

Random Forest achieves the highest accuracy among default models.

This model is then saved as:

customer_churn_model.pkl



6️⃣ Model Evaluation

Metrics used:

Accuracy Score

Confusion Matrix

Classification Report (Precision, Recall, F1)

You can evaluate the model on test data using:

accuracy_score(y_test, y_test_pred)
confusion_matrix(y_test, y_test_pred)
classification_report(y_test, y_test_pred)



7️⃣ Building the Predictive System

To make predictions on new customer data:

Load the saved model and encoders

Create a customer input dictionary

Convert it to a DataFrame

Apply saved encoders

Run predict() and predict_proba()

The notebook demonstrates this fully.

Predicted output includes:

Churn / No Churn

Probability of the prediction



▶️ Running the Project
1. Clone the repository
git clone https://github.com/thnguyen0405/CUSTOMER-CHURN-PREDICTION
cd CUSTOMER-CHURN-PREDICTION

2. Install dependencies
pip install -r requirements.txt

3. Open the notebook
jupyter notebook customer_churn.ipynb


Run all cells to reproduce the project.



📦 Saved Files
✔ customer_churn_model.pkl

The trained Random Forest model.

✔ encoders.pkl

All label encoders used for categorical columns
(ensures consistent encoding during prediction).



📈 Results

Random Forest performed best with the highest CV accuracy

SMOTE significantly improved minority class performance

Final prediction system correctly outputs:

Churn or Not

Confidence probability
