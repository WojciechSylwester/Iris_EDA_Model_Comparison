## 🌺 Iris EDA + Model Comparison
### Summary
The goal of this project is to classify the Iris species. To achieve this, I understand the data by exploratory data analysis and make insights about it. Baseline models unable me to analyse errors of the models. I handle with these errors by using feature engineering. To achieve better accuracy, I perform hyperparameter tuning. Finally, I check the score using learning curves and compare the models.
## Project Description
### Technologies
* Python
* Scikit-Learn
* Pandas
* Seaborn
* Matplotlib
* Numpy
* Jupyter
## Get Data
Dataset derives from the Kaggle dataset about Iris Species.
The dataset contains data about the length and width of sepal and petal.

https://www.kaggle.com/datasets/uciml/iris

## Exploratory Data Analysis
Boxplots shows that one of the three species has different Sepal values.
I confirmed that in plot of relationship between the petal width and length

![image](https://user-images.githubusercontent.com/61654792/176556227-6f345a6a-3916-46f4-8c77-fd8bce2cae77.png)

## Baseline Models
In this section I train a few different models with their default settings. After that I compare accuracy of these models.

In my process SVC has the highest accuracy - **96%**. Behind them are Logistic Regression, KNN and Decision Tree.

## Error Analysis
I use confusion matrix to analyse the errors of our models and make better performance of them.

```python
Confusion Matrix Logistic Regression 
[[38  0  0]
 [ 0 39  3]
 [ 0  3 37]]
Confusion Matrix KNN 
[[38  0  0]
 [ 0 40  2]
 [ 0  4 36]]
Confusion Matrix SVM 
[[38  0  0]
 [ 0 40  2]
 [ 0  2 38]]
Confusion Matrix Decision Tree 
[[38  0  0]
 [ 0 38  4]
 [ 0  4 36]]
Confusion Matrix Random Forest 
[[38  0  0]
 [ 0 38  4]
 [ 0  4 36]]
 ```
“Iris-setosa” haven't got errors, but “Iris-versicolor” and “Iris-virginica” have a few errors. It corresponds with plots what I make in the EDA section. In order to make better distinguish the last two classes, I use feature engineering.

## Feature Engineering
I make new features by raise to the third power Petal features and divide them by other features.

This has resulted in higher performance of the models.

## Learning Curve
For a few models, learning curves indicate on a good fit. However, I can make it better during hyperparameter tuning by decrease the bias.
Next two models indicate an overfitting. In order to improve performance, high variance should be reduced.
#### Good Fit

![image](https://user-images.githubusercontent.com/61654792/176555878-d3e6f4f2-6569-4926-b923-9f360d008d2d.png)


#### Overfitting
![image](https://user-images.githubusercontent.com/61654792/176555802-b5a5a3f5-6c60-406c-a010-a697b78ae39e.png)


## Hyperparameter Tuning

Almost every model achieves a better validation score.

On the left - model with hyperparameter tuning.

On the right - default model.

![image](https://user-images.githubusercontent.com/61654792/176555636-b496471f-a785-437d-bcb8-5dc288fe37e0.png)


