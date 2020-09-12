---
layout: post
title:  "Gaussian Model"
date:   2020-09-07 11:11:03 -0400
categories: pattern recognition
---
![](https://github.com/zyz9066/zyz9066.github.io/blob/master/images/train2.png)
## Bayesian decision theory
Consider the two-dimensional data points from two classes $$\omega_1$$ and $$\omega_2$$ below, and each of them come from a Gaussian distribution $$p(x\mid\omega_k)\sim \mathcal{N}(\mu_k, \Sigma_k)$$

| $$\omega_1$$ | $$\omega_2$$ |
|(0,0)|(6,9)|
|(1,1)|(8,10)|
|(2,2)|(9,10)|
|(3,2)|(9,11)|
|(4,2)|(10,10)|
|(5,3)|(11,12)|
||(12,12)|
||(12,13)|

Calculate the mean and covariance matrix for each class:

```python
import numpy as np

w1 = np.array([(0, 0), (1, 1), (2, 2), (3, 2), (4, 2), (5, 3)])
w2 = np.array([(6, 9), (8, 10), (9, 10), (9, 11), (10, 10), (11, 12), (12, 12), (12, 13)])

# print mean
print("Mean of w1: ", w1.mean(0))
print("Mean of w2: ", w2.mean(0))

# print covariance matrix
print("Covariance Matrix of w1:\n", np.cov(w1, rowvar=False))
print("Covariance Matrix of w2:\n", np.cov(w2, rowvar=False))

# print determinant
print("Determinant of covariance matrix 1: %.4f" % np.linalg.det(np.cov(w1, rowvar=False)))
print("Determinant of covariance matrix 2: %.4f" % np.linalg.det(np.cov(w2, rowvar=False)))

# print inverse matrix
print("Inverse Matrix of covariance matrix 1:\n", np.linalg.inv(np.cov(w1, rowvar=False)))
print("Inverse Matrix of covariance matrix 2:\n", np.linalg.inv(np.cov(w2, rowvar=False)))
```

```sh
Mean of w1:  [2.5        1.66666667]
Mean of w2:  [ 9.625 10.875]
Covariance Matrix of w1:
 [[3.5        1.8       ]
 [1.8        1.06666667]]
Covariance Matrix of w2:
 [[4.26785714 2.51785714]
 [2.51785714 1.83928571]]
Determinant of covariance matrix 1: 0.4933
Determinant of covariance matrix 2: 1.5102
Inverse Matrix of covariance matrix 1:
 [[ 2.16216216 -3.64864865]
 [-3.64864865  7.09459459]]
Inverse Matrix of covariance matrix 2:
 [[ 1.21790541 -1.66722973]
 [-1.66722973  2.82601351]]
```

## Parametric models
Consider Gaussian density models in different dimensions as following:

```python
# raw data
w1 = np.array([(0.42, -0.087, 0.58),
      (-0.2, -3.3, -3.4),
      (1.3, -0.32, 1.7),
      (0.39, 0.71, 0.23),
      (-1.6, -5.3, -0.15),
      (-0.029, 0.89, -4.7),
      (-0.23, 1.9, 2.2),
      (0.27, -0.3, -0.87),
      (-1.9, 0.76, -2.1),
      (0.87, -1.0, -2.6)])

w2 = np.array([(-0.4, 0.58, 0.089),
      (-0.31, 0.27, -0.04),
      (0.38, 0.055, -0.035),
      (-0.15, 0.53, 0.011),
      (-0.35, 0.47, 0.034),
      (0.17, 0.69, 0.1),
      (-0.011, 0.55, -0.18),
      (-0.27, 0.61, 0.12),
      (-0.065, 0.49, 0.0012),
      (-0.12, 0.054, -0.063)])

w3 = np.array([(0.83, 1.6, -0.014),
      (1.1, 1.6, 0.48),
      (-0.44, -0.41, 0.32),
      (0.047, -0.45, 1.4),
      (0.28, 0.35, 3.1),
      (-0.39, -0.48, 0.11),
      (0.34, -0.079, 0.14),
      (-0.3, -0.22, 2.2),
      (1.1, 1.2, -0.46),
      (0.18, -0.11, -0.49)])
```

Then find the maximum likelihood values $$\hat{\mu}$$ and $$\hat{\sigma}^2$$ for each of the three features $$x_i$$ individually of category $$\omega_1$$ above:

```python
import numpy as np

print('mu1: ', w1.mean(0))
print('var1: ', w1.var(0))
```

```sh
mu1:  [-0.0709 -0.6047 -0.911 ]
var1:  [0.90617729 4.20071481 4.541949  ]
```

Then apply two-dimensional Gaussian data $$p(x)\sim \mathcal{N}(\mu, \Sigma)$$ to each of the three possible pairings of two features for $$\omega_1$$:

```python
from sklearn.covariance import EmpiricalCovariance
cov = EmpiricalCovariance()

cov.fit(w1[:, :-1])
print("mu12: ", cov.location_)
print("Sigma12:\n", cov.covariance_)

cov.fit(w1[:, 1:])
print("\nmu23: ", cov.location_)
print("Sigma23:\n", cov.covariance_)

cov.fit(w1[:, [0,-1]])
print("\nmu13: ", cov.location_)
print("Sigma13:\n", cov.covariance_)
```

```sh
mu12:  [-0.0709 -0.6047]
Sigma12:
 [[0.90617729 0.56778177]
 [0.56778177 4.20071481]]

mu23:  [-0.6047 -0.911 ]
Sigma23:
 [[4.20071481 0.7337023 ]
 [0.7337023  4.541949  ]]

mu13:  [-0.0709 -0.911 ]
Sigma13:
 [[0.90617729 0.3940801 ]
 [0.3940801  4.541949  ]]
```

Apply to full three-dimensional Gaussian data for $$\omega_1$$:

```python
cov.fit(w1)
print("mu1: ", cov.location_)
print("Sigma1:\n", cov.covariance_)
```

```sh
mu1:  [-0.0709 -0.6047 -0.911 ]
Sigma1:
 [[0.90617729 0.56778177 0.3940801 ]
 [0.56778177 4.20071481 0.7337023 ]
 [0.3940801  0.7337023  4.541949  ]]
```

Assume the three-dimensional model is separable, so that $$\Sigma = \text{diag}(\sigma_1^2, \sigma_2^2, \sigma_3^2)$$. Estimate the mean and the diagonal components of $$\Sigma$$ in data $$\omega_2$$:

```python
print("mu2: ", w2.mean(0))
print("Sigma2:\n", np.diag(w2.var(0)))
```

```sh
mu2:  [-0.1126   0.4299   0.00372]
Sigma2:
 [[0.05392584 0.         0.        ]
 [0.         0.04597009 0.        ]
 [0.         0.         0.00726551]]
```

Compare results for the mean $$\mu_i$$ and the variance $$\sigma_i$$ of each feature:

```python
print('mu1:', w1.mean(0))
print('mu2:', w2.mean(0))
print('mu3:', w3.mean(0))
print('var1: ', w1.var(0))
print('var2: ', w2.var(0))
print('var3: ', w3.var(0))
```

```sh
mu1: [-0.0709 -0.6047 -0.911 ]
mu2: [-0.1126   0.4299   0.00372]
mu3: [0.2747 0.3001 0.6786]
var1:  [0.90617729 4.20071481 4.541949  ]
var2:  [0.05392584 0.04597009 0.00726551]
var3:  [0.30186081 0.64496409 1.26214164]
```

## EM algorithm
Use same data points above, suppose that ten data points in category $$\omega_1$$ come from a three-dimensional Gaussian. However, there is no access to the $$x_3$$ components for the even-numbered data points. Use EM algorithm to estimate the mean and covariance of the distribution. Start estimate with $$\mu_0=0$$ and $$\Sigma=I$$, the three-dimensional identity matrix:

```python
w1m = np.array([[0.42, -0.087, 0.58],
      [-0.2, -3.3, np.nan],
      [1.3, -0.32, 1.7],
      [0.39, 0.71, np.nan],
      [-1.6, -5.3, -0.15],
      [-0.029, 0.89, np.nan],
      [-0.23, 1.9, 2.2],
      [0.27, -0.3, np.nan],
      [-1.9, 0.76, -2.1],
      [0.87, -1.0, np.nan]])

w1m[np.isnan(w1m)] = np.nanmean(w1m[:,-1])

from sklearn.mixture import GaussianMixture

mix = GaussianMixture(means_init=np.zeros((1, 3)), precisions_init=[np.eye(3)])

mix.fit(w1m)
print(mix.means_)
print(mix.covariances_)
```

```sh
[[-0.0709 -0.6047  0.446 ]]
[[[0.90617829 0.56778177 0.707406  ]
  [0.56778177 4.20071581 0.4143502 ]
  [0.707406   0.4143502  1.150433  ]]]
```

Compare final estimate with the case when there is no missing data:

```python
mix.fit(w1)
print(mix.means_)
print(mix.covariances_)
```

```sh
[[-0.0709 -0.6047 -0.911 ]]
[[[0.90617829 0.56778177 0.3940801 ]
  [0.56778177 4.20071581 0.7337023 ]
  [0.3940801  0.7337023  4.54195   ]]]
```
