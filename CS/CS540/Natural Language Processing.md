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
<!--SR:!2025-10-02,4,272-->

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
<!--SR:!2025-10-02,4,272--> 

## Bigram Model (k=1)
?
- Present depends on immediate past
- Given a letter, what's the probability of the next letter being __ ?
<!--SR:!2025-10-02,4,272-->

## n-gram Model
?
- k = n-1
	- Allows for more expressive sentence
	- Harder to estimate
	- Training --> count
<!--SR:!2025-10-02,4,272--> 

## n-gram Training
?
- The issue with just counting is that we have to multiply tiny numbers
	- For this we use logs and add instead of multiplying
- For n-grams with zero probability
	- We solve by using smoothing, adding 1 to the numerator and V (number of words in vocabulary) to denominator
	- This ensures the probability adds up to 1
<!--SR:!2025-10-02,4,272-->

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
<!--SR:!2025-10-02,4,272-->

## Representing Words
?
- Random Variables
- One-hot vectors
	- Vector of dimension being the number of words in vocabulary
	- For "dog", a single entry of 1 (rest are zero) represents it within vocabulary
<!--SR:!2025-10-02,4,272-->

## Smarter Representations
?
- *Distributional Semantics* account for relationships between words
	- Representation for objects that relate to each other must be similar
		- Dense vectors/*Word embeddings*
		- Each object is represented by a vector with probability entries per some group
<!--SR:!2025-10-02,4,270-->

## Training Word Embeddings
?
- How do we fine these embeddings?
	- Based on observed data and applied training
- Word2vec was a famous approach
	- Calculates likelihood*:
		- $L(\theta)=\prod_{t=1}^T \prod_{-a\leq j\leq a} P(w_{t+j}|w_{t},\theta)$
		- Where theta is our word vectors
		- First prod denotes all positions
		- Second prod represents windows of length 2a
		- w_t is the word we're focusing in corpus
			- check a previous words and a words after w_t
		- Predicts the context words around w_t
			- t increments each time and it slides the window
	- So what is the probability of this?
		- Let v_w and u_w be two vectors that denote center/context
			- ![[Pasted image 20250927151802.png]]
			- If dot product of u and c is large, it means they have a higher similarity
<!--SR:!2025-09-29,1,232-->

## Transformers
?
- Special model architectures based on attention
	- Sophisticated types of neural networks
<!--SR:!2025-10-02,4,272-->