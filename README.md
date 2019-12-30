# Car Evaluation

Evaluate a car based on its characteristics using classification with Tensorflow2.0.

## Background

**Tensorflow2.0** is the latest version of ***Google***'s flagship deep learning platform.

* Uses Keras API as its default library for training classification and regression models.
* Problem with earlier versions of TensorFlow was the complexity of model creation. 

## Dependencies

* TensorFlow 2.0
* Pandas
* Numpy
* Matplotlib
* Seaborn
* Scikit-learn

`pip install -r requirements.txt`

To make sure TensorFlow2.0 is installed: `pip install --upgrade tensorflow`

## Dataset

* Car Evaluation Dataset: https://www.kaggle.com/elikplim/car-evaluation-data-set
  * Saved in: *data/car_evaluation.csv*
* Details: https://archive.ics.uci.edu/ml/datasets/car+evaluation
  * **price**: the buying price of the car)
  * **maint**:  the maintenance cost
  * **doors**: number of doors
  * **persons**: the seating capacity
  * **lug_capacity**: the luggage capacity
  * **safety**: measure of how safe the car is
  * **output**: the condition of the car

## Data Analysis

### Distribution of output

* 70% are in unacceptable condition
* 20% cars are in acceptable conditions
* The percentage of cars in good and very good condition is very low

### Distribution of values of other features

* Price: low, medium, high, very high: each 25%
* Maintenance: low, medium, high, very high: each 25%
* Doors: 2, 3, 4, 5 or more: each 25%
* Persons: 2, 4, more: each 33.33%
* Luggage capacity: small, big, medium: each 33.33%
* Safety: low, medium, high: each 33.33%

## Data Preprocessing

All the features are categorical

* Convert the categorical columns into numeric
  * ***One-hot encoding***: For each unique value in the categorical column, a new column is created. For the rows in the actual column where the unique value existed, a 1 is added to the corresponding row of the column created for that particular value. 
* Prepare features and labels

## Split data into Training and Test sets

* Training set = 80%
* Test set = 20%

## Create model

* Using **Keras** functional API
* Input layer
* 2 Hidden layers with 15 and 10 neurons respoectively and ReLU activation function
* Output with 4 neurons for 4 label values and Softmax activation function
* Loss function = categorical cross-entropy
* Optimizer = Adam
* Evaluation metric = accuracy

## Train the model

* Epochs = 100
* Validation data = 20% of training data

