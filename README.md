# Prediction-of-Emp-Salary-using-ANN

🧹 Preprocessing Steps

- Preparing the data to ensure it's clean, consistent, and suitable for training an ANN model:

- 📥 Data Import Dataset is read into a DataFrame for analysis.

- 🔍 Initial Inspection Data types, column names, and unique values are checked to understand the structure.

- ❌ Missing Values Check Dataset is scanned for null values; none found, so no imputation is necessary.

- 🏷️ Categorical to Numerical Conversion LabelEncoder is applied to transform categorical variables (like Position, Education, etc.) into numerical format for compatibility with the ANN.

- 🔄 Feature Scaling MinMaxScaler is used to normalize the features to a 0–1 range, which improves convergence and stability during neural network training.

- 📊 Splitting Features and Target Data is divided into:

- X: Features

- y: Target variable (Salary)
