
# Loss Function of Logistic Regression

Hi guys! We all know that in Machine Learning, we use MLE as the loss function of Logistic Regression, but why we choose to use it? Let's take a look!




## Step1. Model Definition


For a binary classification problem, the logistic regression model predicts the probability that a given input \( x \) belongs to the class labeled as "1". This probability can be written as:

![](https://latex.codecogs.com/gif.latex?P%28y%3D1%20%7C%20x%3B%20%5Ctheta%29%20%3D%20%5Csigma%28%5Ctheta%5ET%20x%29%20%5C)

where sigma is the logistic function, theta is the parameter vector, and x is the feature vector. The logistic function is defined as:

![](https://latex.codecogs.com/gif.latex?sigma%28z%29%20%3D%20%5Cfrac%7B1%7D%7B1%20&plus;%20e%5E%7B-z%7D%7D)

The probability of the negative class (where \( y = 0 \)) is then:

![](https://latex.codecogs.com/gif.latex?%5C%20P%28y%3D0%20%7C%20x%3B%20%5Ctheta%29%20%3D%201%20-%20%5Csigma%28%5Ctheta%5ET%20x%29%20%5C)


## Step 2: Likelihood Function
The likelihood function L for all observations is the product of individual probabilities for all observations:

![](https://latex.codecogs.com/gif.latex?%7BL%7D%28%5Ctheta%29%20%3D%20%5Cprod_%7Bi%3D1%7D%5E%7Bn%7D%20P%28y_i%20%7C%20x_i%3B%20%5Ctheta%29%5E%7By_i%7D%20%5Ccdot%20%281%20-%20P%28y_i%20%7C%20x_i%3B%20%5Ctheta%29%29%5E%7B%281%20-%20y_i%29%7D%20%5C)


## Step 3: Log-Likelihood Function
Taking the logarithm of the likelihood function gives us the log-likelihood function:

![](https://latex.codecogs.com/gif.latex?%5C%20%5Cell%28%5Ctheta%29%20%3D%20%5Clog%20%5Cmathcal%7BL%7D%28%5Ctheta%29%20%3D%20%5Csum_%7Bi%3D1%7D%5E%7Bn%7D%20%5Cleft%5B%20y_i%20%5Clog%28%5Csigma%28%5Ctheta%5ET%20x_i%29%29%20&plus;%20%281%20-%20y_i%29%20%5Clog%281%20-%20%5Csigma%28%5Ctheta%5ET%20x_i%29%29%20%5Cright%5D%20%5C)

## Step 4: Negative Log-Likelihood Function


Since we want to minimize the loss function (rather than maximize the likelihood), we take the negative of the log-likelihood function, which is called the negative log-likelihood (NLL):

![](https://latex.codecogs.com/gif.latex?%5C%20%5Ctext%7BNLL%7D%28%5Ctheta%29%20%3D%20-%5Cell%28%5Ctheta%29%20%3D%20-%5Csum_%7Bi%3D1%7D%5E%7Bn%7D%20%5Cleft%5B%20y_i%20%5Clog%28%5Csigma%28%5Ctheta%5ET%20x_i%29%29%20&plus;%20%281%20-%20y_i%29%20%5Clog%281%20-%20%5Csigma%28%5Ctheta%5ET%20x_i%29%29%20%5Cright%5D%20%5C)


## Step 5: Loss Function for Logistic Regression

To obtain the loss function that we use for logistic regression, we usually average the negative log-likelihood over all observations, which gives us the Cross-Entropy Loss or Log Loss:

![](https://latex.codecogs.com/gif.latex?%5C%20%5Ctext%7BLoss%7D%28%5Ctheta%29%20%3D%20%5Cfrac%7B1%7D%7Bn%7D%20%5Ctext%7BNLL%7D%28%5Ctheta%29%20%3D%20-%5Cfrac%7B1%7D%7Bn%7D%20%5Csum_%7Bi%3D1%7D%5E%7Bn%7D%20%5Cleft%5B%20y_i%20%5Clog%28%5Csigma%28%5Ctheta%5ET%20x_i%29%29%20&plus;%20%281%20-%20y_i%29%20%5Clog%281%20-%20%5Csigma%28%5Ctheta%5ET%20x_i%29%29%20%5Cright%5D%20%5C)
This loss function is what we aim to minimize during the training of a logistic regression model. It's convex, so gradient descent or other optimization algorithms can find the global minimum.