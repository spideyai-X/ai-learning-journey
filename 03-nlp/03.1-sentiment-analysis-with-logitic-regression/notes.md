The first course will talk about the calculus of a good or negative sentiment about a word in a sample text.
We will make our first translation system and make use of 'locality sensitive hashing' to improve the performance of  
nearest neighbor search.

Logistic regression is a good model because it's easy to train, we will use it to analyze sentiments.

# Supervised ML & Sentiment Analysis

![Supervised ML Training](../images/supervised-ml-training.png)

Supervised ML is : features X, labels Y.  
Goal is to minimize our cost using for example gradient descent. We reach this goal when the expected value Y and the predicted value Y hat is minimized.

For example, this tweet : I am happy because I am learning NLP  
To define if it is a Positive:1 or Negative:0 class, we will use logistic regression.

![Sentiment Analysis Class](../images/sentiment-analysis-class.png)

There is the way to do.  
First, we to extract meaningful features. (Here, the tweet is the feature X) -> Next, training the classifier minimizing the cost. -> Then, classify the tweet.

0 : negative sentiment  
1 : positive sentiment

# Vocab & Feature Extraction

## Vocab

Here, we will see how can we represent a text as a vector  
The way is to build a vocabulary, so we could encode any text as an array of number called vector 

For our tweet for example, there is how it works : 

![Vector representation](../images/vector-representation.png)

Tweets[] is the array of all tweets we can have.  
V (vocabulary) array represent the vocabulary of these tweets, it's like each word of all tweets will be in V. But a word is not repeted > 1 time.

## Feature extract & sparse representation

For our example tweet, we will create a feature vector by checking for the presence of each word from our vocabulary (V) in that tweet.  

![Feature extraction](../images/feature-extraction.png)

1 : the word appears in our tweet
0 : the word not appears in our tweet

That's called a SPARSE representation.

Sparse representation size is equal to our whole V. That's mean we could have a lot of zeros.
In logistic regression, model will train on n+1 parameters, with n equal to V size.  
Care, for remember, V size is count of unique word in the tweets array for example here.

The problem is : for large vocalubary array, we could get too much large training time !

![Problem with sparse representation](../images/problem-with-sparse-representation.png)

## Negative & positive freq

We create a frequency directionnary, with PosFreq and NegFreq, which maps a word to a number of time that word shows up.
Then, we can compare these 2 features. That's how we could measure positive & negative frequency.

![Word frequency](../images/word-frequency.png)

## Feature extract with freq

We previously learn how to encode a tweet as a vector of dimension V.
We will learn how to encode a tweet as a vector of dimension 3.

We surely have much more speed because instead of training on V features, we'll only have 3 features.

Let's say that our dictionnary mapping is called "freqs".

X = features
m = tweet number m

- The first feature is a bias unit : 1  
- The second feature is a sum of every Positive Frequencies for every unique word on tweet m  
- The third feature, is a sum of every Negative Frequencies for every unique word on tweet m  

![Calculus](../images/feature-extraction-calculus.png)

So for example, for our tweet, sum of Positive Frequency is 8, because we sum all PosFreq(1).

![Positive Frequency calculus](../images/pos-freq-sum.png)

And it's the same way for the third feature.
That's computes give us a vector Xm = [1,8,11]

![Features 3D vector](../images/features-3d-vector.png)

# Preprocessing

## Stop words, punctuation, handles & URLs

We could now ask ourself what about stop words & punctuation, that are words with no meaning.  
We most remove them. To keep the main subject of the corpus.

![Stop words & punctuation removal](../images/stop-words-removing.png)

It's the exact same way for URLs etc..
![Handles & Urls removing](../images/handles-and-urls-removing.png)

Key point : we have to adapt these rules to our context. Maybe our goal is to capt punctuation so we should not remove them, care to that.

Here, we don't care about handles & urls for sentiment analysis.

## Stemming & lowercasing

Stemming in NLP : transforming any word to its spacetemp (= set of characters used to constuct the word and its derivative)

Example : for the word tuning.
tun with suffixe e = tune
tun with suffixe ed = tuned
tun with suffixe ing = tuning

After processing stemming on corpus, 'tune', 'tuned' and 'tuning' words will be reduced to the term 'tun'.

![Stemming](../images/stemming.png)

So, our vocab would be significantly reduced if we perform this process to every words of the corpus.
In addition, if we really want to loose no information, we have to lowercase every words. So, for example, the words 'GREAT', 'Great' & 'great' will be treated as the exact same word.