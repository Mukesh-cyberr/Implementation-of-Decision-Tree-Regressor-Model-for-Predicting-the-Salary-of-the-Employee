# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the libraries and read the data frame using pandas.
2. Calculate the null values present in the dataset and apply label encoder.
3. Determine test and training data set and apply decison traaaaaaaaaee regression in dataset.
4. Calculate Mean square error,data prediction and r2.

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: MUKESH RAJ D
RegisterNumber:  212224100038
*/
```
```

import pandas as pd
data=pd.read_csv("Salary.csv")
data.head()

data.info

data.isnull().sum()

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()

x=data[["Position","Level"]]
y=data[["Salary"]]

from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test=train_test_split(x,y,test_size=0.2,random_state=2)

from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)

from sklearn import metrics
mse=metrics.mean_squared_error(y_test, y_pred)
mse

r2=metrics.r2_score(y_test,y_pred)
r2

dt.predict([[5,6]])
```

## Output:
<img width="627" height="325" alt="Screenshot 2026-02-12 152750" src="https://github.com/user-attachments/assets/12cd2221-0342-45c1-97df-8618dee4e931" />

<img width="417" height="289" alt="Screenshot 2026-02-12 152806" src="https://github.com/user-attachments/assets/87dd58d8-b979-4a79-9228-5452937e8718" />

<img width="248" height="160" alt="Screenshot 2026-02-12 152822" src="https://github.com/user-attachments/assets/1aa5309c-068f-4c73-8a14-693c3b961d52" />

<img width="1260" height="709" alt="Screenshot 2026-02-12 153013" src="https://github.com/user-attachments/assets/d4192016-0f5b-48df-868f-432c93c81d04" />



## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
