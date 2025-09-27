## Definition
?
- Field of study that gives the computer the ability to learn without being explicitly programmed
	- Parsing data to learn key patterns and/or understand the data to perform inference/reasoning

## Taxonomy of ML
?
- Supervised Learning
	- Has labels and numerical data
- Unsupervised Learning
- Reinforcement Learning

## Examples
?
- Based on the previous likings of the user, predict whether this user will like a song "A" 
- Image classification
	- Feed training data to the machine to train it to recognize what class a given image is
	- Test by providing different data
		- *Generalizing* (when testing performs good), *overfitting* (when trained but doesn't perform well on testing)
	- Bounding boxes to classify a part of the image
## Data Representation
?
- Represent data using vectors where the dimension is called a feature dimension

## Types of Supervised Learning Algorithms
?
- Classification
	- e.g image classification
	- Label is *discrete*
- Regression
	- e.g housing price prediction
	- Given x, predict y
	- Train first from sample data and then by the line of best fit predict the label for a new house
	- Have *continuous* values for the label
	- x can be of higher dimension and is denoted as *features*
	- y is denoted as *label*/output and is usually of single dimension


## Training Data for Supervised Learning
?
- Collection of input instances to the learning algorithm
- *Experience* given to a learning algorithm