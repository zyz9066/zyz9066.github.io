---
layout: post
title:  "Logistic Regression and Application"
date:   2020-08-30 16:11:03 -0400
categories: statistical learning
---
# Logistic Regression and Classification
Logistic regression is a machine learning classification algorithm used to assign observations to a discrete set of classes. Some of the well known examples of this kind of classification are **email spam or ham, transactions fraud, tumor malignant or benign**. Given a feature vector *X* and a qualitative response *Y* taking values in the set *C={C_1, ..., C_k}*, a classification task is to build a function $$f:X\to Y$$ (classifier) that takes the feature vector $$X$$ as input and predicts the value for $$Y$$, i.e. $$Y\in C$$.

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
