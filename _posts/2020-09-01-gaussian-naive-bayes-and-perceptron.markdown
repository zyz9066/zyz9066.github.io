---
layout: post
title:  "Gaussian Naive Bayes and Perceptron"
date:   2020-09-01 11:11:03 -0400
categories: data mining
---
## Objective
To understand the basic machine learning algorithms, here I implement the following two algorithms, from scratch, in *Python* (using only *Numpy* import). And test these algorithms on the [*Linnerrud*](https://scikit-learn.org/stable/datasets/index.html#linnerrud-dataset "Linnerrud dataset") dataset (import using: `from sklearn.datasets import load_linnerud`) using all 3 attributes, and only the chinups outcome. Define new vector assigning binary classes to the outcome of chinups as follows:

`if (chinups > median(chinups)) then chinups = 0 else chinups = 1`

```python
import numpy as np
from sklearn.datasets import load_linnerud

(data, target) = load_linnerud(return_X_y=True)

chinups = data[:,0]
median = np.median(chinups)
chinups = np.where(chinups > median, 1, 0)
```

then use these classes to build the probability table and train the perceptron.

## Gaussian Naive Bayes
Gaussian Naive Bayes is a probabilistic modeling algorithm.



# A) Gaussian Naive Bayes (probabilistic modeling)

```python
class GNB():
    def __init__(self):
        self._mu0 = []
        self._mu1 = []
        self._sigma0 = []
        self._sigma1 = []
        self._prior = {}

    def _prior_prob(self, y):
        unique, counts = np.unique(y, return_counts=True)
        prob = counts/len(y)
        return dict(zip(unique, prob))

    def fit(self, X, y):
        self._mu0 = np.mean(X[y==0], axis=0)
        self._mu1 = np.mean(X[y==1], axis=0)
        self._sigma0 = np.std(X[y==0], axis=0)
        self._sigma1 = np.std(X[y==1], axis=0)
        self._prior = self._prior_prob(y)

    def pred(self, x):
        x0 = x
        x1 = x
        probs0 = np.ones(x.shape)
        probs1 = np.ones(x.shape)
        for i in range(x.shape[1]):
            gaussian0 = lambda x: 1/(np.sqrt(2*np.pi)*self._sigma0[i])*np.exp((-(x-self._mu0[i])**2)/(2*self._sigma0[i]**2))
            gaussian1 = lambda x: 1/(np.sqrt(2*np.pi)*self._sigma1[i])*np.exp((-(x-self._mu1[i])**2)/(2*self._sigma1[i]**2))
            v_gaussian0 = np.vectorize(gaussian0)
            v_gaussian1 = np.vectorize(gaussian1)
            probs0[:,i] = v_gaussian0(x0[:,i])
            probs1[:,i] = v_gaussian1(x1[:,i])

        likeli0 = np.prod(probs0, axis=1)*self._prior[0]
        likeli1 = np.prod(probs1, axis=1)*self._prior[1]
        post = likeli1 / (likeli0+likeli1)
        return post
```

```python
gnb = GNB()
gnb.fit(target, chinups)
outputs = gnb.pred(target)
print(((outputs > 0.5) == chinups).sum() / len(chinups))
```

```sh
0.7
```

## Perceptron
Perceptron learning rule is linear modeling algorithm.

```python
class Perceptron(object):
    # if perceptron does not converge run for 1000 iterations
    def __init__(self, iters=1000):
        self._iters = iters
        self._weights = []

    def fit(self, X, y):
        # set all weights to zero
        self._weights = np.zeros(X.shape[1]+1)
        # until all instances in training set are correctly classified
        # or run enough iterations
        for _ in range(self._iters):
            y_pred = self.pred(X)
            y_pred = y_pred>0
            if np.all(y_pred==y):
                break

            for inst, label in zip(X, y): # for each instance
                pred = self._pred(inst)
                if pred != label: # if inst is classed incorrectly
                    # if inst belongs to first class, add to weight vec
                    # else subtract it from weight vec
                    self._weights[1:] += (label - pred) * inst
                    self._weights[0] += (label - pred)

    def _pred(self, inst):
        prediction = np.dot(inst, self._weights[1:]) + self._weights[0]
        if prediction > 0:
            prediction_class = 1
        else:
            prediction_class = 0
        return prediction_class

    def pred(self, x):
        weighted_sums = np.dot(x, self._weights[1:]) + self._weights[0]
        return weighted_sums
```

```python
perceptron = Perceptron()
perceptron.fit(target, chinups)
outputs = perceptron.pred(target)
print(((outputs > 0) == chinups).sum() / len(chinups))
```

```sh
0.5
```
