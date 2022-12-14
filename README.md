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

Those methods were quite interesting to explore with Logistic Regression staying on the top of our ranking when used with the following parameters: solver='lbfgs', cv=10, max_iter=500, random_state = 50 no split

As the BERT model took up to 11 hours to calculate, you can find our [saved_weights.pt here](https://filesender.switch.ch/filesender2/?s=download&token=94bd9337-3af3-4a96-bc01-5f3f02df82d1)

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
We can notice that the best and most reliable model is the logistic regression with cross validation. However this model was very sensitive to variations in iterations or Cross-Validation

The second model with the most consistent accuracy was the SVM, as it's accuracy was usually above 50%. By fine tuning it, we could get decent results.

By increasing the training set, in principle we got better results. For future improvements on the model we should hence collect more data that could have identifiable levels.
Additionnal data cleaning should have been used in retrospect, unfortunately after our first attempt in it (removal of integers and times), we found are accuracy significantly decreasing (to about 30%).

## Our video recap
[Can be found here](https://youtu.be/mWCkUTexAu8)
