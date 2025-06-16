# Prediction-of-Emp-Salary-using-ANN

 Preprocessing Steps

- Preparing the data to ensure it's clean, consistent, and suitable for training an ANN model:

-  Data Import Dataset is read into a DataFrame for analysis.

-  Initial Inspection Data types, column names, and unique values are checked to understand the structure.

-  Missing Values Check Dataset is scanned for null values; none found, so no imputation is necessary.

-  Categorical to Numerical Conversion LabelEncoder is applied to transform categorical variables (like Position, Education, etc.) into numerical format for compatibility with the ANN.

-  Feature Scaling MinMaxScaler is used to normalize the features to a 0–1 range, which improves convergence and stability during neural network training.

-  Splitting Features and Target Data is divided into:

- X: Features

- y: Target variable (Salary)

 Modeling with ANN + Optuna Optimization

•	Building and tuning an Artificial Neural Network using Optuna for automated hyperparameter search:

 Hyperparameter Optimization via Optuna

•	An objective function is defined to construct a Keras Sequential ANN using variable parameters.
•	Optuna runs multiple trials to find the best combination of:
•	Number of hidden layers
•	Neurons per layer
•	Dropout rate
•	Learning rate
•	Activation functions
•	The trial with the lowest validation loss is selected as the best configuration.

 Model Construction with Best Params

•	A new ANN model is built using the best hyperparameters suggested by Optuna.
•	Adam optimizer is configured with the tuned learning rate.
•	Dropout layers are added to mitigate overfitting.

 Model Training & Evaluation

•	Model is trained on the preprocessed dataset.
Evaluated using:
•	Mean Absolute Error (MAE)
•	R² score
•	Training vs validation loss to monitor overfitting

 Deployment Steps

•	Final steps to prepare the pipeline for real-world predictions:

 New DataFrame Creation

•	A new input DataFrame (df1) is defined with relevant features like age, gender, education, job title, and experience.

 Feature Engineering

•	Added a new column: avg_experience_by_job, which stores the average experience for each job title.
•	Added count_by_gender_edu, representing how many individuals share the same gender and education level.

 Dropping Unused Columns

•	Removed Job Title as it has been encoded indirectly through aggregated features.

 Encoding Categorical Variables

•	Used get_dummies with drop_first=True to convert categorical columns into numeric format.

 Feature Scaling

•	Applied the pre-fitted MinMaxScaler to transform the new input data (df1) to the same scale as the training data.

 Prediction with Trained Model

•	Used the saved ANN model (best_model) to predict salaries based on the scaled features.

 Output Formatting

•	Created a new DataFrame (df_test_scaled) containing the scaled inputs and the model’s predicted salary for each individual.
