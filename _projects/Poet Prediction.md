---
layout: page
title: Poet Prediction Using N-Grams
description: Predicting the poets of poems using uni-gram and bi-gram models
img: assets/img/poems.png
importance: 7
category: Artificial Intelligence
---
[Link to Github](https://github.com/mahvash-siavashpour/ngram-persian-poem-classification) <br>
This code uses some train sets to learn the n-grams (n=1, 2). These train sets each include the poems from a specific poet. Then the code uses these n-grams in a back-off model to predict the poets of each poem. It also provides accuracy for the model.

## Data
The training dataset contains poems from 3 great Persian poets: Ferdowsi, Hafez, Molavi. The training dataset can be found [here](https://github.com/mahvash-siavashpour/ngram-persian-poem-classification/tree/master/train_set).<br>
Sample poems:
<br>
{% include figure.html path="assets/img/poems.png" title="table" class="img-fluid rounded z-depth-1" %}
<br>

## Building the Model
In order to perform calculations, it was necessary to build unigram and bigram models for each of the poets according to their training data. In Unigram, words with a frequency of less than 2 were removed to make calculations more accurate. Then, with the backoff model calculations were done for each stanza. The model (poet) that produced the highest probability is considered as the label of this stanza.
Calculations of probabiliry: <br>
```
probability[poet] *= (frqBi * landa[2] + frqUni * landa[1] + landa[0] * e)
```

## Parameter Tuning
Parameter tuning was done on the coefficients of the backoff model. According to that the best values for Landa and e coefficients was tobtained. The results show that the highest coefficient value should be given to the bigram model and the value of e should be small. Also the bigram and unigram coefficients should be chosen close to each other. In explanation, it can be stated that bigram and unigram models are both powerful, but bigram is more accurate because it takes into account 2 tokens. Therefore, assigning a higher coefficient to it will make our answer more accurate. The coefficients for the unigram are smaller because the goal is to use the unigram if the combination is not available in the bigram. e is also important when our word is not in any of the models. So this value should be close to the lowest probability of occurrence of each word, so a small number should be chosen.<br>

Comparing modes, it can also be said that when the difference between unigram and bigram coefficients increases, it causes a decrease in accuracy. The reason is that we rely too much on one model, and if the probability of a combined event in that model is zero, then the accuracy of our model decreases because this probability may be a high in another model, which we ignored. Here it is necessary to mention that, as we observed in different cases, if the difference of coefficients between different models is large and a higher coefficient is assigned to the unigram model, we have a higher accuracy in comparison with the case of assigning a larger coefficient to the bigram model. In order to explain this, it can be stated that the probability of seeing a word in the unigram model is higher than seeing a combination in the bigram model. <br>

And it can also be claimed that the accuracy decreases in very large or very small e's. The reason is that when e is large, the effect of e is greater than the effect of other elements, which can be problematic because e is a constant coefficient that has nothing to do with our models.
Also, in very small e, the value of e is close to zero, which causes an error in our total probability.
