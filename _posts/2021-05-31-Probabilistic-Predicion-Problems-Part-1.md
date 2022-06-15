---
layout: post
title: Probabilistic Prediction Problems - Part 1
---

I have been wanting to organize my notes on _probabilistic prediction problems_ into a more structured and "high level" format. This post is a result of this, and the notes are primarily from Probabilistic Machine Learning (Introduction and Advanced) by Kevin Murphy, Statistical Rethinking by Richard McElreath, and Bayesian Modeling and Computation in Python.

## The Problem with Parameters and Probabilistic Models

Three main monsters when it comes to "modeling":
1. Overfitting
2. Underfitting
3. Con-founders

The goal of the model should be stated before you choose your methods to tame these monsters:
- Is the goal _predictive power_?
- Is the goal to understand _causes_?

Adding variables and parameters to a model can help to reveal hidden effects and improve estimates. However, more parameters always results in a better model "fit". While more complex models fit the data better, they often predict new data worse. Models that have many parameters tend to overfit more than simpler models. 

It is possible to assume the set of possible actions is to pick a class label (or "reject" option) in classification or a real valued scalar as in a point estimate of a parameter. However, it is also possible to assume the set of possible actions is to pick a probability distribution over some value of interest (paramter or class label). That is, we want to perform probabilistic  prediction or probabilistic forecasting rather than predicting a single value / scalar. From a decision theoretic approach, we assume the true state of nature is a distribution, $h = p(Y | x)$, with the action being another distribution, $a = q(Y|x)$.

## Scores and Rules

### Proper Scoring Rules

Maximizing a proper scoring rule will force the model to match the true probabilities, i.e., the probabilities are calibrated. For example, when the weather person states the probability of rain is $70\%$, then it should rain about $70\%$ of the time. 

The following are proper scoring "loss functions":

- Negative log-likelihood
- Cross entropy
- Brier score

### Evaluating Predictive Models

- Log-scoring rule

### Model Selection and Evaluation

To check the results of modeling and inference, we would like to know how well a model fits observed data $x$, which we can quantify with the evidence or marginal likelihood.