---
title: "R Statistical Handbook"
description: "A guide to statistics in R"
slug: "rstats"
image: pic07.jpg
keywords: ""
categories: 
    - ""
    - ""
date: 2017-10-31T22:42:51-05:00
draft: false
---

# This page shows how to perform a number of statistical tests using R. Each section gives a brief description of the aim of the statistical test, when it is used, an example showing the R commands and R output with a brief interpretation of the output

## Setup

```
hsb2 <- within(read.csv("your_csv_here.csv"), {
    race <- as.factor(race)
    schtyp <- as.factor(schtyp)
    prog <- as.factor(prog)
})

attach(hsb2)
```

## One sample t-test

```
t.test(write, mu=50)

```

## One sample median test

```
wilcox.test(write, mu=50)
```

## Binomial test

```
prop.test(sum(female), length(female), p=05)
```

## Chi-square goodness of fit

```
chisq.test(table(race), p = c(10, 10, 10, 70)/100)
```

## Two independent samples t-test

```
t.test(write ~ female)
```

## Wilcoxon-Mann-Whitney test

```
wilcox.test(write ~ female)
```

## Chi-square test

```
chisq.test(table(female, schtyp))
```

## Fisher's exact test

```
fisher.test(table(race, schtyp))
```

## One-way ANOVA

```
summary(aov(write ~ prog))
```

## Kruskal Wallis test

```
kruskal.test(write, prog)
```

## Paired t-test

```
t.test(write, read, paired=TRUE)
```

## Wilcoxon signed rank sun test

```
wilcox.test(write, read, paired=TRUE)
```

## McNemar test

```
X <- matrix(c(172, 7, 6, 15), 2, 2)
mcnemar.test(X)
```

## Friedman test

```
friedman.test(cbind(read, write, math))
```

## Correlation

```
cor(read, write)
```

```
cor.test(read, write)
```

## Simple linear regression

```
lm(write ~ read)
```

## Non-parametric correlation

```
cor.test(write, read, method = "spearman")
```

## Simple logistic regression

```
glm(female ~ read, family = binomial)
```

## Multiple regression

```
lm(write ~ female + read + math + science + socst)
```

## Analysis of covariance

```
summary(aov(write ~ prog + read))
```

## One-way MANOVA

```
summary(manova(cbind(read, write, math) ~ prog))
```