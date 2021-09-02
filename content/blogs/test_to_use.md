---
title: "Choosing the Right Statistical Test"
description: "Unsure of what test to work with? Use this resource"
slug: "choosing"
image: pic10.jpg
keywords: ""
categories: 
    - ""
    - ""
date: 2017-10-31T21:28:43-05:00
draft: false
---

|Number of Dependent Variables | Nature of Independent Variables | Nature of Dependent Variables | Test(s) |
| :-------------------------:| :-----------------------------:| :----------------------------:| :---------:|
|**1** | **1 population** | interval & nominal | one-sample t-test |
| | | ordinal or interval |one-sample median|
| | | categorical with 2 categories | binomial test |
| | | categorical | Chi-square goodness of fit |
| | **Independent groups, 2 levels** | interval & nominal | 2 independent sample t-test |
| | | ordinal or interval | Wilcoxon-Mann Whitney test |
| | | categorical | Chi-square test |
| | | categorical | Fisher's exact test|
| | **Independent groups, 2 or more levels** | interval & nominal | one-way ANOVA |
| | | ordinal or interval | Kruskal Wallis |
| | | categorical | Chi-square test|
| | **Dependent/matched groups, 2 levels** | interval & nominal | paired t-test |
| | | ordinal or interval | Wilcoxon signed ranks test |
| | | categorical | McNemar|
| | **Dependent/matched groups, 2 or more levels** | interval & normal | one-way repeated measures ANOVA |
| | | ordinal or interval | Friedman test|
| | | categorical with 2 categories | repeated measures logistic regression|
| | **2 or more independent variables** | interval & normal | factorial ANOVA
| | | ordinal or interval | ordered logistic regression
| | | categorial with 2 categories | factorial logistic regression|
| | **1 interval independent variable** | interval & normal | correlation|
| | | interval & nromal | simple linear regression |
| | | ordinal or interval | non-parametric correlation |
| | | categorical | simple logistic regression|
| | **1 or more interval independent variables &/or 1 or more categorical independent variables** | **interval & normal** | multiple regression |
| | | | analysis of covariance |
|| | **categorical**| multiple logistic regression|
| | | | discriminant analysis |
|**2+** | **1 independent variable with 2 or more levels** | interval and normal | one-way MANOVA |
| | **2+** | interval & normal | multivariate multiple linear regression |
| | **0** | interval & normal | factor analysis |
| **2 sets of 2+** | **0** | interval and normal | canonical correlation |
