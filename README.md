# Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored

## AIM:
To write a program to predict the marks scored by a student using the simple linear regression model.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Load the dataset into a DataFrame and explore its contents to understand the data structure.
2.Separate the dataset into independent (X) and dependent (Y) variables, and split them into training and testing sets.
3.Create a linear regression model and fit it using the training data.
4.Predict the results for the testing set and plot the training and testing sets with fitted lines.
5.Calculate error metrics (MSE, MAE, RMSE) to evaluate the model’s performance.

## Program:
```
/*
Program to implement the simple linear regression model for predicting the marks scored.
Developed by: LOGA SRI M
RegisterNumber:  212225230153

import pandas as pd
import numpy as np 
import matplotlib.pyplot as plt
from sklearn.metrics import mean_absolute_error, mean_squared_error
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
df = pd.read_csv('exp_2_dataset_student_scores.csv')   
print("First 5 rows:\n", df.head(), "\n")
print("Last 5 rows:\n", df.tail(), "\n")
X = df.iloc[:, :-1].values   
Y = df.iloc[:, -1].values    
print("X (features):", X.flatten())
print("Y (targets):", Y)
X_train, X_test, Y_train, Y_test = train_test_split(X, Y, test_size=1/3, random_state=0)
print("\nTraining samples:", len(X_train), " Testing samples:", len(X_test))
regressor = LinearRegression()
regressor.fit(X_train, Y_train)
Y_pred = regressor.predict(X_test)
print("\nPredicted values:", np.round(Y_pred, 2))
print("Actual values   :", Y_test)
plt.figure(figsize=(6,4))
plt.scatter(X_train, Y_train, color="orange", label="Training data")
plt.plot(X_train, regressor.predict(X_train), color="red", label="Fitted line")
plt.title("Hours vs Scores (Training set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.legend()
plt.grid(True)
plt.show()
order = np.argsort(X_test.flatten())
X_test_sorted = X_test.flatten()[order]
Y_test_sorted = Y_test[order]
Y_pred_sorted = Y_pred[order]
plt.figure(figsize=(6,4))
plt.scatter(X_test, Y_test, color="blue", label="Test data")
plt.plot(X_test_sorted, Y_pred_sorted, color="green", label="Predictions")
plt.title("Hours vs Scores (Testing set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.legend()
plt.grid(True)
plt.show()
mae = mean_absolute_error(Y_test, Y_pred)
mse = mean_squared_error(Y_test, Y_pred)
rmse = np.sqrt(mse)
print("\nMean Absolute Error (MAE):", mae)
print("Mean Squared Error (MSE):", mse)
print("Root Mean Squared Error (RMSE):", rmse)
new_hours = np.array([[2.5], [8.0]])   # shape must be (n_samples, 1)
pred_new = regressor.predict(new_hours)
print("\nPredictions for new hours", new_hours.flatten(), "=>", np.round(pred_new,2))
*/
```

## Output:

<img width="823" height="545" alt="image" src="https://github.com/user-attachments/assets/79f7328e-ff4d-4294-956c-cd308c6750f9" />

<img width="922" height="218" alt="image" src="https://github.com/user-attachments/assets/60c1f1d0-2953-49d1-b97a-3d8051b8b792" />

<img width="962" height="515" alt="image" src="https://github.com/user-attachments/assets/e6e4e787-07bd-4a08-96d6-7a47aaafa933" />

<img width="707" height="551" alt="image" src="https://github.com/user-attachments/assets/6ad2d8a5-7ded-4601-adfb-83ef1089b827" />

<img width="845" height="571" alt="image" src="https://github.com/user-attachments/assets/5b6d2561-1509-451d-8460-913a0bcc4bc5" />

<img width="868" height="512" alt="image" src="https://github.com/user-attachments/assets/48852ad9-0d06-4d15-85c0-ab98f5daa73e" />

## Result:
Thus the program to implement the simple linear regression model for predicting the marks scored is written and verified using python programming.
