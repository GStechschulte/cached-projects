---
layout: post
title: Probabilistic Prediction Problems - Part 1
categories: [probability]
---

Part one deals with why parameters (or latent variables) are problematic and common loss functions for comparing two probability distributions. 

# Probabilistic Prediction Problems

## The Problem with Parameters

Three main monsters when it comes to "modeling":
1. Overfitting
2. Underfitting
3. Con-founders

The goal of the model should be stated before you choose your methods to tame these monsters:
- Is the goal _predictive power_?
- Is the goal to understand _causes_?

Regarding monster (1), adding variables and parameters to a model can help to reveal hidden effects and improve estimates. However, more parameters always results in a better model "fit". While more complex models fit the data better, they often predict new data worse. Models that have many parameters tend to overfit more than simpler models. Generally, fit is measured by how well the model can retrodict the data used to fit the model. A common metric for this is "variance explained", $R^2$. Monster (2) hurts, too. Underfitting produces models that are inaccurate both within and out of sample. Underfit models have learned too little, whether that be from uninformative features or too simple a model.

So, how to navigate overfitting and underfitting? First, pick a criterion of model performance as the target—_what do you want the model to be good at?_ Information theoretic based methods can provide a common and useful target.  

## Distributions over Actions

It is possible to assume the set of possible actions is to pick a class label (or "reject" option) in classification or a real valued scalar as in a point estimate of a parameter. However, it is also possible to assume the set of possible actions is to pick a probability distribution over some value of interest (paramter or class label). That is, we want to perform probabilistic  prediction or probabilistic forecasting rather than predicting a single value / scalar. From a decision theoretic approach, we assume the true state of nature is a distribution, $h = p(Y | x)$, with the action being another distribution, $a = q(Y|x)$. The goal is to be as close to the true state of nature $p$ with our approximation $q$. Therefore, we want to pick $q$ to minimize $\mathbb{E}\ell(p, q)$ for a given $x$. 



### KL-Divergence, Cross-Entropy, and Log-Loss

KL-divergence, cross-entropy, and log-loss are common loss functions are comparing two distributions.


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