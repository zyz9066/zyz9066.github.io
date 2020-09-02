---
layout: post
title:  "Validation Techniques in Scikit-learn"
date:   2020-09-01 18:11:03 -0400
categories: data mining
---
## Goal
Here just test a variety of classifiers on different datasets in *sklearn*, and test validation techniques (cross-validation, ROC, t-test). It mainly just involves calling *sklearn* functions and displaying results.

## Classification and Regression
### Classifiers
- Import and load the toy datasets from *sklearn*:

```python
import numpy as np
from sklearn.datasets import load_boston, load_iris, load_diabetes, load_digits, load_linnerud, load_wine, load_breast_cancer

boston = load_boston()              # regression
iris = load_iris()                  # classification
diabetes = load_diabetes()          # regression
digits = load_digits()              # classification
linnerud = load_linnerud()          # regression
wine = load_wine()                  # classification
cancer = load_breast_cancer()       # classification
```

Import and initialize the following classifers from *sklearn*:

```python
from sklearn.naive_bayes import GaussianNB
from sklearn import tree
from sklearn.neighbors import KNeighborsClassifier
from sklearn.neural_network import MLPClassifier

gnb = GaussianNB() # probabilistic
tree = tree.DecisionTreeClassifier() # divide and conquer
knn = KNeighborsClassifier(3, n_jobs=-1) # instance based
mlp = MLPClassifier() # neural network
```

Train and run each classifier on each classification dataset separately, resulting in a 4x4 matrix (dataset rows, classifier columns) showing the accuracy of 4 classifiers above on each classification dataset (here use entire dataset, no test/train split). Classification datasets are iris, digits, wine, breast cancer:

```python
clfs = [gnb, tree, knn, mlp]
clf_data = [iris, digits, wine, cancer]
clf_mat = np.zeros((len(clf_data), len(clfs)))

for i in range(len(clf_data)):
    for j in range(len(clfs)):
        clf_mat[i,j] = clfs[j].fit(clf_data[i].data, clf_data[i].target).score(clf_data[i].data, clf_data[i].target)

print(clf_mat)
```

```sh
[[0.96       1.         0.96       0.97333333]
 [0.85809683 1.         0.9933222  1.        ]
 [0.98876404 1.         0.87078652 0.92696629]
 [0.94200351 1.         0.95606327 0.92091388]]
```

Using the 4x4 matrix above, we can get classifier which has highest mean accuracy across all datasets and dataset which has the highest mean accuracy across all classifiers:

```python
datasets = ['iris', 'digits', 'wine', 'cancer']
classifiers = ['GaussianNB', 'DecisionTree', 'KNN', 'MLP']
print('Classifier with highest mean accuracy:', classifiers[np.argmax(np.mean(clf_mat, axis=0))])
print('Dataset with highest mean accuracy:', datasets[np.argmax(np.mean(clf_mat, axis=1))])
```

```sh
Classifier with highest mean accuracy: DecisionTree
Dataset with highest mean accuracy: iris
```
### Regressors
Import and initialize the following regression algorithms from *sklearn*:

```python
from sklearn import linear_model
from sklearn import svm

reg = linear_model.LinearRegression(n_jobs=-1) # linear regression
svr = svm.SVR(gamma='scale') # support vector regression
```

Create a 3x2 matrix (dataset rows, classifier columns) showing accuracy of 2 regression techniques above on the three regression datasets:

```python
# can't use loop because of irregular formats (linnerud)
from sklearn.metrics import mean_squared_error
regs = [reg, svr]
regsets = [boston, diabetes, linnerud]
regmat = np.zeros((len(regsets), len(regs)))

# fit boston with linear regression
reg = regs[0].fit(regsets[0].data,regsets[0].target)
regmat[0,0] = mean_squared_error(reg.predict(regsets[0].data),regsets[0].target)

# fit boston with svr
reg = regs[1].fit(regsets[0].data,regsets[0].target)
regmat[0,1] = mean_squared_error(reg.predict(regsets[0].data),regsets[0].target)

# fit diabetes with linear regression
reg = regs[0].fit(regsets[1].data,regsets[1].target)
regmat[1,0] = mean_squared_error(reg.predict(regsets[1].data),regsets[1].target)

# fit diabetes with svr
reg = regs[1].fit(regsets[1].data,regsets[1].target)
regmat[1,1] = mean_squared_error(reg.predict(regsets[1].data),regsets[1].target)

# fit chinups of linnerud with linear regression
reg = regs[0].fit(regsets[2].target,regsets[2].data[:,0])
regmat[2,0] = mean_squared_error(reg.predict(regsets[2].target),regsets[2].data[:,0])

# fit chinups of linnerud with support vector regression
reg = regs[1].fit(regsets[2].target,regsets[2].data[:,0])
regmat[2,1] = mean_squared_error(reg.predict(regsets[2].target),regsets[2].data[:,0])

print('Score matrix:\n', regmat)
```

```sh
Score matrix:
 [[  21.89483118   66.81823779]
 [2859.69039877 4701.3346054 ]
 [  17.53272477   27.93451036]]
```
Get regression technique which has lower mean-squared error (across datasets) and dataset which has lowest mean squared-error (across regression methods):

```python
datasets = ['boston', 'diabetes', 'linnerud']
regs = ['LinearRegression', 'SupportVectorRegression']
print('Technique with lower MSE:', regs[np.argmin(np.mean(regmat, axis=0))])
print('Dataset with lowest MSE:', datasets[np.argmin(np.mean(regmat, axis=1))])
```

```sh
Technique with lower MSE: LinearRegression
Dataset with lowest MSE: linnerud
```

## California housing predictions and validation
Fetch California housing dataset:

```python
from sklearn.datasets import fetch_california_housing
cali = fetch_california_housing()
```

Using Gaussian Naive Bayes, for each instance output a probability that the house is worth over $$\$300$$k (target variable is in units of $$\$100,000$$'s):

```python
from sklearn.naive_bayes import GaussianNB
gnb = GaussianNB()
gnb.fit(cali.data, cali.target>3)
probs = gnb.predict_proba(cali.data)[:,1]
print('Probabilities:', probs)
```

```sh
Probabilities: [0.99466801 0.9864607  0.97258702 ... 0.02976907 0.02970739 0.02622946]
```

Perform k-fold (k=10) cross-validation (CV) and find the average error across all folds on the test set (using GNB) and the resubstitution error (error on training data):

```python
from sklearn.model_selection import cross_val_score
scores = cross_val_score(gnb, cali.data, cali.target>3, cv=10)
print('Average error:', 1-np.mean(scores))
print('Resubstitution error:', 1-(np.mean(gnb.score(cali.data, cali.target>3))))
```

```sh
Average error: 0.16167635658914725
Resubstitution error: 0.13187984496124028
```

Calculate the ROC area using the training data above, this is also known as the 'resubstitution ROC area' (ROC from training data), i.e., train GNB on all the instances, then calculate ROC area using probabilities from predictions on instances that GNB was trained on. Also try to increase the area under ROC by denoising or removing attributes, of performing some other type of transformation (PCA, PLS, etc.):

```python
from sklearn import metrics

def roc_auc(clf,data,target):
    clf.fit(data,target)
    fpr, tpr, thresholds = metrics.roc_curve(target,clf.predict_proba(data)[:,1])
    return metrics.auc(fpr,tpr)

aucs = []

clf = GaussianNB();
aucs.append(roc_auc(clf,cali.data,cali.target>3))

from sklearn.decomposition import MiniBatchDictionaryLearning, FactorAnalysis, FastICA, PCA
n_comps = 8
denoise_types = ['no denoising','dictionary','fastica','factor','pca','pls','cca','plsr','plssvd']

dlearn_data = MiniBatchDictionaryLearning(n_components=n_comps).fit_transform(cali.data)
aucs.append(roc_auc(clf,dlearn_data,cali.target>3))

fastica_data = FastICA(n_components=n_comps).fit_transform(cali.data)
aucs.append(roc_auc(clf,fastica_data,cali.target>3))

factored_data = FactorAnalysis(n_components=n_comps).fit_transform(cali.data)
aucs.append(roc_auc(clf,factored_data,cali.target>3))

pca_data = PCA(n_components=n_comps).fit_transform(cali.data)
aucs.append(roc_auc(clf,pca_data,cali.target>3))

from sklearn.cross_decomposition import PLSCanonical, PLSRegression, CCA, PLSSVD
pls_data = PLSCanonical(n_components=n_comps).fit_transform(cali.data,cali.target)[0]
aucs.append(roc_auc(clf,pls_data,cali.target>3))

cca_data = CCA(n_components=n_comps).fit_transform(cali.data,cali.target)[0]
aucs.append(roc_auc(clf,cca_data,cali.target>3))

plsr_data = PLSRegression(n_components=n_comps).fit_transform(cali.data,cali.target)[0]
aucs.append(roc_auc(clf,plsr_data,cali.target>3))

plssvd_data = PLSSVD(n_components=n_comps).fit_transform(cali.data,cali.target)[0]
aucs.append(roc_auc(clf,plssvd_data,cali.target>3))

print([m+': '+str(n) for m,n in zip(denoise_types,aucs)])
```

```sh
['no denoising: 0.8484153867233061', 'dictionary: 0.5750434485532642', 'fastica: 0.876654999405524', 'factor: 0.8468747448035487', 'pca: 0.8798073504148549', 'pls: 0.8477933977311624', 'cca: 0.8958197952520863', 'plsr: 0.8819438023594859', 'plssvd: 0.8477934054878935']
```
It seems [canonical correlation](https://en.wikipedia.org/wiki/Canonical_correlation) analysis is most useful (on this dataset).

Using the following 3 classifiers:
1. Gaussian Naive Bayes (same as above)
2. k-nearest neighbour with k=3 (it can output probabilities)
3. random forest (also outputs probabilities)

```python
from sklearn.naive_bayes import GaussianNB
from sklearn.neighbors import KNeighborsClassifier
from sklearn.ensemble import RandomForestClassifier
forest = RandomForestClassifier(n_estimators=100, n_jobs=-1)
kneigh = KNeighborsClassifier(n_neighbors=3, n_jobs=-1)
gnb = GaussianNB()
```

Calculate the average ROC area over 10 tests sets from 10-fold CV, (i.e., calculate one ROC area for each fold's test set predictions, and average them all to create a single ROC area):

```python
from sklearn.model_selection import StratifiedKFold
from sklearn.metrics import roc_curve, auc
aucs = np.zeros([3,10])
cv = StratifiedKFold(n_splits=10)
cali = fetch_california_housing()
X = cali.data
y = cali.target > 3
i = 0
clfcount=0
for clf in [forest,kneigh,gnb]:
    for train, test in cv.split(X, y):
        probas_ = clf.fit(X[train], y[train]).predict_proba(X[test])
        fpr, tpr, thresholds = roc_curve(y[test], probas_[:, 1])
        roc_auc = auc(fpr, tpr)
        aucs[clfcount,i] = roc_auc
        i += 1
    clfcount += 1
    i=0

clf_types = ['forest','kneigh','gnb']
print([m+':'+str(n) for m,n in zip(clf_types,np.mean(aucs,axis=1))])
```

Random Forest algorithm gives the highest area under average ROC curve from results.

```sh
['forest:0.8841087896768691', 'kneigh:0.6391597057782026', 'gnb:0.8236029346715579']
```

Using a t-test, compare the algorithm with the highest performance to the other two algorithms, and check if the p-value is significant (p<0.05):

```python
from scipy import stats

t_1,p_1 = stats.ttest_ind(aucs[0,:],aucs[1,:])
t_2,p_2 = stats.ttest_ind(aucs[0,:],aucs[2,:])
print('P-value (RF vs GNB): {} < 0.05 => {}'.format(p_2, p_2<0.05))
print('P-value (RF vs KNN): {} < 0.05 => {}'.format(p_1, p_1<0.05))
```

```sh
P-value (RF vs GNB): 0.041641516493412564 < 0.05 => True
P-value (RF vs KNN): 9.452363626206385e-11 < 0.05 => True
```
