# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### AHMED KAMEL HASSAN

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
first i realized that my prediction need to be more accurate and i got it after creating additional feature

### What was the top ranked model that performed?
WeightedEnsemble_L3 it the top-ranked model in all my training results

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?


as number of (count) increases, (count) frequency decrease exponentioally
for ['weather'] column, number of records with weather = 1 > 2 > 3 > 4 . 
for['holiday] column, number of records with 0 value much more than that with value = 1
number of records of each season nearby equals.

we add additional features by extracting [year,month,day] from datetime column

### How much better did your model preform after adding additional features and why do you think that is?
after adding additional features as following :
 - root_mean_squared_error decreased from 80 to 16.8
 - r2 raised from 0.8 to 0.99
 - kaggle score become better , decreased from 1.79 to 0.69
I think it happened because the new features we created had a good impact in the prediction process. 

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
model was better before trying different hyper parameters , the score back to increase to 21.77 and the kaggle score become too poor.

### If you were given more time with this dataset, where do you think you would spend more time?
i would spend the additional time in hyper parameter optimizing and try different of them to get best score .

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|default|default|default|1.79062|
|add_features|default|default|default|0.44463|
|hpo|NN epochs:[10], activation:[relu,tanh], num_layer:[100], dropout:[0.0,0.5]|GBM num_boost_round:100, num_leaves:[26,66]|default|0.48679|


### Create a line plot showing the top model score for the three (or more) training runs during the project.

![model_train_score.png](model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

![model_test_score.png](model_test_score.png)

## Summary
creating additiona feature has a good impact in increasing performance and got i better score and prediction 
using hyper parameter optimisation is good but it require to try many hyperparameters to get an acceptable result