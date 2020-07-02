# (Statistical) Learning Theory

## Contents

- Introduction.
- Sequential decision making.
- Expert advice and multi-armed bandits.
- Online convex optimization.
- Contextual bandits.

## Introduction

- Main contributions:
    + Mathematical model of learning and conditions characterizing what can be learned.
    + Choice of learning bias, control of overfitting.
    + SVM, Boosting
- Components:
    <!-- + Feature: $$\mathcal{X} \sim R^d$$. -->
    + Feature: <img src="https://latex.codecogs.com/svg.latex?\Large&space;\mathcal{X}\inR^d"/>
    + Label: regression, classification.
    + Loss function, Square, Zero-one, Hlinge.
    + Model: $$f: \mathcal{X} \rightarrow \mathcal{Y}$$.
    + Train set $$(x_1, y_1) ,\cdot, (x_m, y_m)$$.
    + Learning algorithm: mapping training sets to models for a given loss.
- Others:
    + Sample $$(x, y)$$ is drawn from unknown distribution $$\mathcal{D}$$.
    + Train set is a random sample from $$\mathcal{D}$$.
    + Bayes optimal predictor $$f^* = argmin_{\hat{y} \in \mathcal{Y}} \mathbb{E}[l(Y, \hat{y})|X=x]$$.
- Bias-variance decomposition.