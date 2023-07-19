1. Overview:

The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With your knowledge of machine learning and neural networks, you’ll use the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

From Alphabet Soup’s business team, you have received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as:

EIN and NAME—Identification columns
APPLICATION_TYPE—Alphabet Soup application type
AFFILIATION—Affiliated sector of industry
CLASSIFICATION—Government organization classification
USE_CASE—Use case for funding
ORGANIZATION—Organization type
STATUS—Active status
INCOME_AMT—Income classification
SPECIAL_CONSIDERATIONS—Special considerations for application
ASK_AMT—Funding amount requested
IS_SUCCESSFUL—Was the money used effectively

2. Results:

   Data Preprocessing:

What variable(s) are the target(s) for your model?
 
  IS_SUCCESSFUL
  
What variable(s) are the features for your model?
  
  APPLICATION_TYPE
  
  AFFILIATION
  
  CLASSIFICATION
 
  USE_CASE
  
  ORGANIZATION
  
  STATUS
  
  INCOME_AMT
  
  SPECIAL_CONSIDERATIONS
 
  ASK_AMT
  
What variable(s) should be removed from the input data because they are neither targets nor features?
  
  EIN and NAME 

   Compiling, Training, and Evaluating the Model:


   How many neurons, layers, and activation functions did you select for your neural network model, and why?


The initial model used 2 hidden layers with an 80/30 neuron split. Activation function relu was used as the default for deep learing models.
  
   Were you able to achieve the target model performance?


These parameters yielded only 72% accuaracy, short of the 75% goal.
  
   What steps did you take in your attempts to increase model performance?


Subsequent attempts tried first adding extra hidden layers, then changing activation functions with little to no effect on model accuracy. On the fourth attempt I used the keras tuner library to automatically find the best parameters to optimize the model's performance. 



Summary:


The final model from the keras tuner method achieved 72.9% prediction accuracy with a 0.45 loss. The optimal parameters according to the keras-tuner search were: relu activation function with input node of 46, 5 hidden layers at a 16, 16, 26, 1, 11, neurons split and 50 training epochs. 
