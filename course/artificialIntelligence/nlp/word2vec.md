# word2vec

http://web.stanford.edu/class/cs224n/lecture_notes/cs224n-2017-notes1.pdf

1. [類神經網路 -- word2vec (part 1 : Overview)](http://cpmarkchang.logdown.com/posts/773062-neural-network-word2vec-part-1-overview)
2. [類神經網路 -- word2vec (part 2 : Backward Propagation)](http://cpmarkchang.logdown.com/posts/773231--word2vec-neural-networks-part-2-backward-propagation)
3. [類神經網路 -- word2vec (part 3 : Implementation)](http://cpmarkchang.logdown.com/posts/773558-neural-network-word2vec-part-3-implementation)


1. [Word2Vec Tutorial - The Skip-Gram Model](http://mccormickml.com/2016/04/19/word2vec-tutorial-the-skip-gram-model/)
2. [Word2Vec Tutorial Part 2 - Negative Sampling](http://mccormickml.com/2017/01/11/word2vec-tutorial-part-2-negative-sampling/)
3. [Google's trained Word2Vec model in Python](http://mccormickml.com/2016/04/12/googles-pretrained-word2vec-model-in-python/)

## 3 SVD Based Methods

3.1 Word-Document Matrix
3.2 Window based Co-occurrence Matrix
3.3 Applying SVD to the cooccurrence matrix

## 4 Iteration Based Methods - Word2vec

4.1 Language Models (Unigrams, Bigrams, etc.)
4.2 Continuous Bag of Words Model (CBOW)
4.3 Skip-Gram Model
4.4 Negative Sampling
4.5 Hierarchical Softmax

## skip-gram model

[Word2Vec Tutorial - The Skip-Gram Model](http://mccormickml.com/2016/04/19/word2vec-tutorial-the-skip-gram-model/)

基本概念，但 |W|*|V| 的權重網路很大。

Another place you may have seen this trick is in unsupervised feature learning, where you train an auto-encoder to compress an input vector in the hidden layer, and decompress it back to the original in the output layer. After training it, you strip off the output layer (the decompression step) and just use the hidden layer--it's a trick for learning good image features without having labeled training data.

就像 SVD 一樣， U V UT

n > k < n

We’ll train the neural network to do this by feeding it word pairs found in our training documents. 

wi = nn => v = nn => P(wj|wi)

P(wj|wi) = Probability that if you random choose a word near by wi, that is wj.

When training this network on word pairs, the input is a one-hot vector representing the input word and the training output is also a one-hot vector representing the output word. But when you evaluate the trained network on an input word, the output vector will actually be a probability distribution (i.e., a bunch of floating point values, not a one-hot vector).

...

If you look at the rows of this weight matrix, these are actually what will be our word vectors!

## negative-sampling

[Word2Vec Tutorial Part 2 - Negative Sampling](http://mccormickml.com/2017/01/11/word2vec-tutorial-part-2-negative-sampling/)

如何降低權重網路的大小呢？

論文：[Distributed Representations of Words and Phrases
and their Compositionality](https://arxiv.org/pdf/1310.4546.pdf)

There are three innovations in this second paper:

1. Treating common word pairs or phrases as single “words” in their model.
2. Subsampling frequent words to decrease the number of training examples.
3. Modifying the optimization objective with a technique they called “Negative Sampling”, which causes each training sample to update only a small percentage of the model’s weights.

目前看完 Sampling rate, 待看 Negative Sampling 一節！

##  Word2Vec model 

[Google's trained Word2Vec model in Python](http://mccormickml.com/2016/04/12/googles-pretrained-word2vec-model-in-python/)

https://github.com/chrisjmccormick/inspect_word2vec

https://github.com/chrisjmccormick/inspect_word2vec/tree/master/vocabulary

範例：

Allanah_Munson
WINDS_WILL
nab_sexual_predators
By_Alexandra_Barham
Mayor_Noramie_Jasmin
Chief_Executive_Glenn_Tilton
Neil_Kinnock
Makoto_Tamada_JPN_Konica
abductor_muscle
visit_www.availability.sungard.com
Eury
Greenson
Y1A
Kathy_Dehner
anti_Westernism
...

