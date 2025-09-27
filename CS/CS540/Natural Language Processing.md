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