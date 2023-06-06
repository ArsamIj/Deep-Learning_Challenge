# Deep_Learning_Challenge

The non-profit foundation ‘Alphabet Soup’ wanted a tool to help it select the applicants for funding with the best chance of success in their ventures. With use of machine learning and neural network, the features provided in the dataset were used to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup. 

## Objective
  
From the Alphabet Soup’s business team, the CSV contained more than 34,000 organizations that received funding from Alphabet Soup over the years. Within the dataset are columns that captures the metadata about each organization, which are encompassed in the target and features variables, outlined below:

* Identification columns
* Alphabet Soup application type
* Affiliated sector of industry
* Government organization classification
* Use case for funding
* Organization type
* Active status
* Income classification
* Special consideration for application
* Funding amount requested
* Was the money used effectively


### Data Preprocessing:

* Removed data: `EIN`, `NAME`, as they are neither targets nor features; however, `NAME` was added back into the Optimization Models for binning purposes.
* Cut-off points to bin ‘rare’ categorical variables together in a new value, `Other` for both `CLASSIFICATION` and `APPLICATION_TYPE`
* Used `pd.get_dummies` to converted categorical data to numeric
* Target variable: `IS_SUCCESSFUL`
* Feature variables: `APPLICATION_TYPE`, `AFFILIATION`, `CLASSIFICATION`, `USE_CASE`, `ORGANIZATION`, `STATUS`, `INCOME_AMT`, `SPECIAL_CONSIDERATIONS`, `ASK_AMT`
* Split the preprocessed data into features and target arrays, followed by splitting in to training and testing datasets 

### Compiling, Training and Evaluating the Model

**Model:**

* (2) hidden layers with 80 and 30 neurons. 
Hidden layer activation functions of ‘ReLU’ was used as it is faster to compute and does not activate all the neurons at the same time. 
Output node was 1 as this is a binary classifier model with only one output; was the funding application successful, yes or no. The activation function that was used was ‘Sigmoid’ as this model output is a binary classification between 0 and 1. 

* Model prediction accuracy was below the threshold of 75% at 72.8%, therefore, further optimization is required. 

**Optimization Models**
* As noted above, in the preprocessing stage, `NAME` was added back for binning purposes.
* An automated model optimizer was used to obtain the most accurate model possible via a Keras Sequential Model. 
* Hyperparameter options were provided and a search for the best hyperparameters was performed.

* Although all optimizations exceeded the goal of 75%, the best optimized model was Optimization 3, which achieved a model accuracy of 79.78%.
