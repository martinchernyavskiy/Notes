## NLP
?
- Definition: combining computing with human language
	- Machines can:
		- Answer questions
		- Summarize or extract information
		- Translate between languages
		- Generate dialogue/language

## Challenges of NLP
?
- Language can be ambiguous 

## Language Models
?
- Use probabilistic models to assign a probability to a sentence W
	- Can calculate probability of a sentence by calculating probability of each word
	- Given 2 words (evidences), what is the probability of third word being __ ?
- Used not only for NLP but also:
	- Parsing, part-of-speech tagging, etc.
	- Q/A answering, translation, summarization, etc.

## Training The Language Model
?
- Use chain rule of probability
	- Estimating these probabilities is given by training in machine learning
	- Can't estimate reliably for long histories
- Make assumptions
	- Markov assumption with shorter history
		- Probability of a word depends on probability of k of previous ones
		- We don't need whole past of previous words, instead we can just pick k that are closest to the one we are making assumption for

## Unigram Model (k=0)
?
- Full independence assumption (meaning present doesn't depend on the past)
	- Based on frequencies alone from 

## Bigram Model (k=1)
?
- Present depends on immediate past
- Given a letter, what's the probability of the next letter being __ ?

## n-gram Model
?
- k = n-1
	- Allows for more expressive sentence
	- Harder to estimate
	- Training --> count 

## n-gram Training
?
- The issue with just counting is that we have to multiply tiny numbers
	- For this we use logs and add instead of multiplying
- For n-grams with zero probability
	- We solve by using smoothing, adding 1 to the numerator and V (number of words in vocabulary) to denominator
	- This ensures the probability adds up to 1

## Language Model Evaluation
?
- Observation
- We train/test on separate data & measure metrics
	- Metrics include:
		- *Extrinsic Evaluation*
			- Pick a task and use model to do the task
			- For two models M1, M2, compare the accuracy for each task
				- Slow, may change relatively
		- *Intrinsic Evaluation: Perplexity*
			- Measures uncertainty
				- PP(W) = P(w1, ... , wn)^(-1/n)
				- Compute average PP(W) for all W from dataset
					- Lower average is better

## Representing Words
?
- Random Variables 
- One-hot vectors
	- Vector of dimension being the number of words in vocabulary
	- For "dog", a single entry of 1 (rest are zero) represents it within vocabulary

## Smarter Representations
?
- *Distributional Semantics* account for relationships between words
	- Representation for objects that relate to each other must be similar
		- 