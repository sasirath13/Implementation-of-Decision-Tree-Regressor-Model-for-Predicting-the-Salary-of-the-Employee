# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
Step-1:
Import the required libraries .

Step-2:
Read the data frame using pandas.

Step-3:
Get the information regarding the null values present in the dataframe.

Step-4:
Apply label encoder to the non-numerical column inoreder to convert into numerical values.

Step-5:
Determine training and test data set.

Step-6:
Apply decision tree regression on to the dataframe.

Step-7:
Get the values of Mean square error, r2 and data predictio

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: SASIDHARAN P
RegisterNumber:  212223080051
*/
import pandas as pd
data=pd.read_csv("/content/Salary.csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()

x=data[["Position","Level"]]
y=data["Salary"]

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)

from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)

from sklearn import metrics
mse=metrics.mean_squared_error(y_test,y_pred)
mse

r2=metrics.r2_score(y_test,y_pred)
r2

dt.predict([[5,6]])

```

## Output:

data.head()

![image](https://github.com/sasirath13/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/160568449/c4f8faef-5b75-4817-900f-b8ca344b9011)

data.info()

![image](https://github.com/sasirath13/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/160568449/5dca71f3-5668-41f7-86f1-804898d082e2)


Isnull() & sum() function

![image](https://github.com/sasirath13/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/160568449/7c566069-883f-4c84-9fdf-dec6e0b8cee0)

data.head() for position

![image](https://github.com/sasirath13/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/160568449/7324080d-99de-48af-95e7-e62bfae2e550)

MSE value

![image](https://github.com/sasirath13/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/160568449/0590958e-73d9-4386-8e28-f0e68c608733)


R2 value

![image](https://github.com/sasirath13/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/160568449/8cabe09b-f196-4293-b589-5c3d522ee39a)

Prediction value

![image](https://github.com/sasirath13/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/160568449/ab49ef27-5ae8-4492-b0be-4aa95666f32e)


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
