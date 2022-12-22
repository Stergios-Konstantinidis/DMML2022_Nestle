# DMML2022_Nestle
## Project done for the Data Mining And Machine Learning course of the masters in Information systems at HEC Lausanne.

### Team Nestle (no affiliation to the company)
#### Julie Bürki
#### Stergios Konstantinidis



#### Scope of the course:
This course is an introductory course in data mining and machine learning.
The aim of the course is to understand the basic terminology of data science and machine learning (regression, classification, visualization, clustering, text analytics), comprehend the potential pitfalls, get a general understanding of how to address real-world problems using Python code.
A tangent goal of this class is to increase confidence in our coding skills and to see and think how innovate in an enterprise using machine learning. (Taken from sylabus)

#### Description of the project:
This project aims to create a method a program that can identify a texts difficulty level in french on the standard language difficulty scale, A1, A2, B1, B2, C1, C1.

In order to do so we were asked to follow specific methods at a first time (first part of the project; \[0:4.6\[ ). Those methods were :
+ Logistic Regression
+ KNN
+ Decision Tree Classifier
+ Random Forest Classifier

At a second time we had to improvise and try additional methods and approach the question as we saw most fit.

#### Our approach:
We decided to focus on 4 additionnal methods:
+ Logistic Regression with Cross Validation
+ Support Vector Machine (SVM)
+ Naive Bayes
+ BERT

Those methods were quite interesting to explore with Logistic Regression staying on the top of our ranking when used with the folowing parameters: solver='lbfgs', cv=10, max_iter=500, random_state = 50 no split

As the BERT model took up to 11 hours to calculate, you can find our [saved_weights.pt here](https://filesender.switch.ch/filesender2/?s=download&token=55519e08-cd9a-4d32-b221-397a3bf34e2c)

#### Our results:

##### BERT
| Model | Batch | Epoch | Specificity      | Accuracy |
|-------|-------|-------|------------------|----------|
| BERT  | 32    | 10    | 0.26             |          |
| BERT  | 1000  | 1000  | 0.32             |          |
| BERT  | 1000  | 100   | Tokenization=50  | 0.33     |
| BERT  | 10000 | 50    | Tokenization=100 | 0.35     |
| BERT  | 1000  | 300   | Tokenization=100 | 0.40     |
