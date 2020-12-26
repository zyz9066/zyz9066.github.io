---
layout: post
title:  "Prediction of liver fibrosis"
date:   2020-09-04 11:11:03 -0400
categories: statistical learning
---
Hepatitis C virus (HCV) infection affects more than 170 million people worldwide. Egypt has the highest prevalence of hepatitis C in the world with prevalence rates reaching 13%-15%. Thus, HCV represents a major public health and economic problem in Egypt. HCV infection is marked by high tendency to persistence and evolution to chronic hepatitis with development of serious consequences such as cirrhosis and liver cancer in some patients. The aim here is to use statistical learning to predict liver fibrosis by discovering the hidden predictive patterns from medical [databases](https://archive.ics.uci.edu/ml/datasets/Hepatitis+C+Virus+%28HCV%29+for+Egyptian+patients).

```python
import pandas as pd

# Easy way to load text data
dataset = pd.read_csv('HCV-Egy-Data.csv')

from sklearn.model_selection import train_test_split, GridSearchCV

X_train, X_test, y_train, y_test = train_test_split(dataset.drop('Baselinehistological staging', axis=1), dataset['Baselinehistological staging'], test_size=0.2)
```

```python
from sklearn.linear_model import LinearRegression

reg = LinearRegression(n_jobs=-1)
reg.fit(X_train, y_train)

print("score of train: " + str(reg.score(X_train, y_train)))
print("score of test: " + str(reg.score(X_test, y_test)))
```

```sh
score of train: 0.02317700812806467
score of test: -0.015362922484045916
```

```python
from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
scaler.fit(X_train)
X_train_std = scaler.transform(X_train)
X_test_std = scaler.transform(X_test)
reg.fit(X_train_std, y_train)
print("score of train_std: " + str(reg.score(X_train_std, y_train)))
print("score of test_std: " + str(reg.score(X_test_std, y_test)))
```

```sh
score of train_std: 0.02317700812806467
score of test_std: -0.015362922483792785
```

```python
from sklearn.svm import SVC
svc = SVC(C=1.0, coef0=0.0, degree=3, gamma='auto', kernel='rbf')
svc.fit(X_train_std, y_train)
print("Training accuracy: " + str(svc.score(X_train_std, y_train)))
print("Validate accuracy: " + str(svc.score(X_test_std, y_test)))
```

```sh
Training accuracy: 0.759927797833935
Test accuracy: 0.26353790613718414
```

```python
svc = SVC(C=1.0, coef0=0.0, degree=3, gamma='auto', kernel='poly')
svc.fit(X_train_std, y_train)
print("Training accuracy: " + str(svc.score(X_train_std, y_train)))
print("Test accuracy: " + str(svc.score(X_test_std, y_test)))
```

```sh
Training accuracy: 0.9657039711191335
Test accuracy: 0.2779783393501805
```

```python
from sklearn.svm import SVR
svr = SVR(C=1.0, coef0=0.0, degree=3, gamma='auto', kernel='rbf')
svr.fit(X_train_std, y_train)
print("Training score: " + str(svr.score(X_train_std, y_train)))
print("Test score: " + str(svr.score(X_test_std, y_test)))
```

```sh
Training score: 0.5123633575720238
Test score: -0.12338287175953577
```

```python
svr = SVR(C=1.0, coef0=0.0, degree=3, gamma='auto', kernel='poly')
svr.fit(X_train_std, y_train)
print("Training score: " + str(svr.score(X_train_std, y_train)))
print("Test score: " + str(svr.score(X_test_std, y_test)))
```

```sh
Training score: 0.7101103374624762
Test score: -0.08247148605051358
```

```python
from keras.models import Sequential
from keras.layers import Dense, BatchNormalization, Dropout

def Model_NN(input_shape):
    model = Sequential()
    model.add(Dense(64,input_dim=input_shape, activation = 'relu'))
    model.add(BatchNormalization())
    model.add(Dropout(0.4))
    model.add(Dense(32))
    model.add(BatchNormalization())
    model.add(Dropout(0.2))
    model.add(Dense(16, activation='relu'))
    model.add(Dropout(0.1))
    model.add(BatchNormalization())
    model.add(Dense(1, activation='linear'))

    model.summary()

    model.compile(loss='mean_squared_error', optimizer='adam', metrics=['accuracy'])
    return model

model = Model_NN(input_shape = X_train_std.shape[1])
model.fit(X_train_std, y_train, epochs = 600)
print(model.evaluate(X_train_std, y_train))
print(model.evaluate(X_test_std, y_test))
```

```sh
[0.3429620656510983, 0.5532491207122803]
[1.485450843611349, 0.256317675113678]
```

```python
from sklearn import tree
dt = tree.DecisionTreeClassifier()
dt.fit(X_train_std, y_train)
print(dt.score(X_train_std, y_train))
print(dt.score(X_test_std, y_test))
```

```sh
1.0
0.19494584837545126
```
