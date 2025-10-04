## Regression
?
- Continuous label
- Goal is to find a mode (function) with minimal loss that maps a feature to a label

## Basic Steps of Supervised Learning
?
- Select model class
- Select loss
- Optimize parameters
- Evaluate output

## Models
?
- Which functions should we consider?
	- If have a function that checks whether x is one of the data points and returns its corresponding label, then though the loss is zero, we're unable to use it to make estimates for new features
- Want to pick a specific class of functions and parameterize it by weights
	- Consider *linear models*
		- Where f(x) = $\theta_{0}+x^T\theta$ and each entry of theta are the weights / parameters
	- Given the regression loss formula, after substituting the above for f(x) we then need to minimize the loss over theta

## How to optimize parameters?
?
- Optimization problem, consider using *gradient descent*
	- Start at initial position and reach local minimum and update parameters so that the initial position would be closer to the local minimum

## Gradient Descent
?
- For one dimension, taking derivative of the function tells how to shift x to make f(x) larger
- For higher dimensions we must use a gradient of f(x) which tells which direction f grows fastest
- ![[Pasted image 20251004065133.png]]
- Large step size could result in ending up at a higher position than the actual local minimum but if the step size is too small, then the algorithm would take a long time

## Train vs. Test
?
- After parameterizing the model, we test it on a reserved test set that wasn't part of the training
- Allows to detect overfitting (when a mode performs well for training data but very poorly for the test data and thus is unable to generalize well)
	- A bigger class of functions is more prone to overfit

## Linear Regression
?
- Simplest form of regression, we need to find constants a, b such that the label is well-approximated by ax_i + b (line of best fit)
- Need a linear combination of x components and intercept (need parameters theta)

## Linear Regression Setup
?
- The goal is to figure out how to minimize square loss 
- To simplify $\theta_{0} + x^T\theta$ we can append 1 at the beginning of the x vector and thus we would have f(x) being equal to just the dot product of the two
.
- We transpose each entry of x to make it a n \* (d+1) matrix and make y label a vector
	- This results in empirical risk $\frac{1}{n}||X\theta-y||^2$ 
	- Can either optimize using Gradient Descent or we can use a closed-form solution
	- $\theta = (X^TX)^-1X^Ty$
		- X^T X might not always be invertible

## Classification
?
- Label is discrete, for the case where y is either 0 or 1
- We need to convert the dot product of transposed theta and x to a probability
- Use logistic function:
	- $p(y=1|x)= \frac{1}{1+\exp(-\theta^Tx)}$
		- Where if inside of exponent is large positive value, the probability gets close to 1 and if large negative, then probability gets close to 0

