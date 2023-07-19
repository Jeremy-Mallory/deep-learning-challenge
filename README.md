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

![model_attempt1](https://github.com/Jeremy-Mallory/deep-learning-challenge/assets/122320256/c6e9ffcd-16d4-4287-9d43-4b5713912c75)

  
   Were you able to achieve the target model performance?


These parameters yielded only 72% accuaracy, short of the 75% goal.

![model#1](https://github.com/Jeremy-Mallory/deep-learning-challenge/assets/122320256/5c3a029d-4f73-4d5c-aa84-1a5dd340fe8a)

  
   What steps did you take in your attempts to increase model performance?


Subsequent attempts tried first adding extra hidden layers.

![model_attempt_3](https://github.com/Jeremy-Mallory/deep-learning-challenge/assets/122320256/90378721-4fda-4d2a-afeb-4d2ae0b03f69)

![model#3png](https://github.com/Jeremy-Mallory/deep-learning-challenge/assets/122320256/de426583-7e21-4c1d-91cc-6809253338b9)


After that, changing activation functions. 

![model_attempt2](https://github.com/Jeremy-Mallory/deep-learning-challenge/assets/122320256/a14bb532-558d-4e72-8a97-b56bf0cb9e79)

![model#2](https://github.com/Jeremy-Mallory/deep-learning-challenge/assets/122320256/b9fecfaa-8270-439d-b618-c5884f8626a9)


On the fourth attempt I used the keras tuner library to automatically find the best parameters to optimize the model's performance. 

![keras_tuner](https://github.com/Jeremy-Mallory/deep-learning-challenge/assets/122320256/9a0a9cf4-d613-41da-b7ef-d112d6a14aa5)

![keras_search](https://github.com/Jeremy-Mallory/deep-learning-challenge/assets/122320256/9620ac1c-351c-489c-9abc-e0a3d667dae1)

![model#4](https://github.com/Jeremy-Mallory/deep-learning-challenge/assets/122320256/ea338474-9fd3-4ffd-8114-1ab432c08f2e)


3. Summary:


The final model from the keras tuner method achieved 72.9% prediction accuracy with a 0.55 loss. The optimal parameters according to the keras-tuner search were: relu activation function with input node of 46, 5 hidden layers at a 16, 16, 26, 1, 11, neurons split and 50 training epochs. I suspect that the next step would be to manipulate the shape of data itself and possibly add more information about each organization in order to build a more accurate model. 
