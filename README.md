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
This project aims to create a program that can identify a texts difficulty level in french on the standard language difficulty scale, A1, A2, B1, B2, C1, C2.

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

##### Logistic Regression
|   Model | CV |    Solver |     Specificity | max_iter | Accuracy |
|--------:|---:|----------:|----------------:|---------:|---------:|
| Log_Reg |  2 |     lbfgs |     Basic model |       10 |   0.4635 |
| Log_Reg |  2 |     lbfgs | Label encoded Y |       10 |   0.4635 |
| Log_Reg |  5 |     lbfgs | Label encoded Y |       10 |   0.4625 |
| Log_Reg |  5 |     lbfgs | Label encoded Y |      100 |   0.4677 |
| Log_Reg |  5 | newton-cg | Label encoded Y |      100 |  0.46770 |
| Log_Reg |  5 |     lbfgs | Label encoded Y |      100 |  0.47083 |
| Log_Reg | 10 |     lbfgs | Label encoded Y |      500 |  0.55208 |


##### Naive Bayes and SVM 
|        Model |                         Specificity | Accuracy |
|-------------:|------------------------------------:|---------:|
| Naives Bayes |                                     |   0.4823 |
| Naives Bayes |                      Train Set= 0.9 |   0.5166 |
|          SVM |                                     |   0.4583 |
|          SVM |                       Train set=0.9 |   0.5270 |
|          SVM | Train set=0.9 & Random state= 77777 |   0.5229 |


##### BERT
| Model | Batch | Epoch | Specificity      | Accuracy |
|-------|-------|-------|------------------|----------|
| BERT  | 32    | 10    | 0.26             |          |
| BERT  | 1000  | 1000  | 0.32             |          |
| BERT  | 1000  | 100   | Tokenization=50  | 0.33     |
| BERT  | 10000 | 50    | Tokenization=100 | 0.35     |
| BERT  | 1000  | 300   | Tokenization=100 | 0.40     |

#### Review and summary of the result tables:
We can notice that the model predicting the best and most reliable model is the logistic regression with cross validation
