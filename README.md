# Loan Status Prediction using ML

In this project, we will check whether the person can be approved for a loan based on their financial features. For this project, we will be using a Support Vector machine model. 

Support Vector Machine (SVM) is a supervised machine learning algorithm used for both classification and regression tasks, but it is most commonly used for classification.

## Notes :-

### 1. `.isnull()` Function
This is function will return the complete DataFrame with `True` or `False` values. If the value is not present (i.e. a Null value), it will show `True`, otherwise `False`.

To check the total number of Null values present in the DataFrame, we use `.isnull().sum()`. This will return Series with the number of Null values in each column (feature).

### 2. Label Encoding
Label encoding is the process of converting categorial values (mostly string values) into numerical value. 

In this DataFrame, the features with categorical values are :-

| Fetures | Possible Values |
| ------- | ---------------- |
| Gender | Male, Female |
| Married | Yes, No |
| Education | Graduate, Not Graduate |
| Self_Employed | Yes, No |
| Property_Area | Rural, Urban |

There are mainly 2 ways to replace these values :- <br>
a. Using Pandas function .replace() <br>
b. Using sklearn's label encdoing function.

Since all the possible values of categorical features are binary, we will replace the string values with ***1*** and ***0***

In `.replace()`, we are using a parameter ***inplace=True*** . We are basically doing this to save the changes permanently in that DataFrame.  

### 3. `value_counts()` Function
We use this function to check the occurences of unique values of a particular column. 

### 4. Count Plot
We use count plot to visualize the frequency of each possible values of a feature. We use a function from the Seaborn, `.countplot()`. 

We can also use this to visualize the frequency of each possible values of a feature along with some sub category using the ***hue*** parameter. In this example, we are trying to see the frequency of males and females (possible values of the feature ***Gender***) along with the ***Loan_status*** feature. This will tell us 4 things :-
1. Number of males who got the loan approved.
2. Number of males who didn't get the loan approved
3. Number of females who got the loan approved.
4. Number of females who didn't get the loan approved

### 5. Creating the Feature DataFrame and Target Series
To do this, we are simply dropping the *Loan_Status* (since that's our Target) and *Loan_ID* (since it's not useful for making any predictions) columns from the dataset  to get the Feature DF and just selecting the *Loan_Status* column for our Target Series.

### 6. Splitting the data
Before we train the model, we need to split the data into 2 sets :-
1. Training set
2. Test or validating set.

To split the data, we are using the function `train_test_split()`.

We are passing 4 parameters in this function :-
1. The feature dataset
2. The target dataset
3. `test_size` : By default it's .25, which means 25% of the dataset will be used for testing and the other 75% for the training.
4. `random_state` : This is to make sure that our data split remains same during every execution.
5. `stratiify` : It basically ensures that the data split have the same proportions every time.

### 7. Training the model
Here, we are creating a model of `svm.SVC()` class. 

***SVC*** stands for Support Vector Classifier. It is the model used for classification by ***SVM***.

We train, predict, and score the model in the same way we train Decision Tree model or Random Forest model (at least at this basic level :) ).

<br><br>

> This project was a complete walkthrough of this [tutorial](https://youtu.be/XckM1pFgZmg?si=4rVzh9ccgwVtxAxZ) by Siddhardhan.
