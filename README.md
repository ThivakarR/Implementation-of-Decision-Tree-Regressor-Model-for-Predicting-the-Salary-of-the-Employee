# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

### Step 1:
Import the libraries and read the data frame using pandas.

### Step 2:
Calculate the null values present in the dataset and apply label encoder.

### Step 3:
Determine test and training data set and apply decison tree regression in dataset.

### Step 4:
Calculate Mean square error,data prediction and r2.

## Program:
```
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: R.THIVAKAR
RegisterNumber:  212222240109
```
```python
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
### data.head():
![Screenshot from 2023-10-16 12-23-04](https://github.com/Gchethankumar/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118348224/ec3b5028-b047-4c7b-a3f4-0a4eedecf3e5)


### data.info():
![Screenshot from 2023-10-16 12-23-12](https://github.com/Gchethankumar/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118348224/98a0431a-7c1b-4fe9-9e05-8b944c979514)


### isnull() and sum():
![Screenshot from 2023-10-16 12-23-21](https://github.com/Gchethankumar/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118348224/d12803bb-a0af-4017-8254-a6d469be0a87)


### data.head() for salary:
![Screenshot from 2023-10-16 12-23-30](https://github.com/Gchethankumar/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118348224/c797a80f-254e-4965-b50c-fda09c1a3016)


### MSE value:
![Screenshot from 2023-10-16 12-23-38](https://github.com/Gchethankumar/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118348224/43ffc290-5c45-4a39-a5d4-33f594a08fe7)


### r2 value:
![Screenshot from 2023-10-16 12-23-46](https://github.com/Gchethankumar/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118348224/84424043-dff1-4cd6-8f9e-09f28ed45b4e)


### data prediction:
![Screenshot from 2023-10-16 12-24-01](https://github.com/Gchethankumar/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/118348224/12b4dedb-40c6-4e17-b0b2-8a6de7aef90c)


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
