---
title: "SAS Statistical Handbook"
description: "A guide to statistics in SAS"
slug: "sasstats"
image: pic08.jpg
keywords: ""
categories: 
    - ""
    - ""
date: 2017-10-31T22:26:13-05:00
draft: false
---

# This page shows how to perform multiple statistical tests using SAS

## One sample t-test

```
proc ttest data = "c:/mydata/data_name" h0 = 50;
  var write;
run;

```

## One sample median test

```
proc univariate data = "c:/mydata/data_name" loccount mu0 = 50;
  var write;
run;
```

## Binomial test

```
proc freq data = "c:/mydata/data_name";
  tables female / binomial(p=.5);
  exact binomial;
run;
```

## Chi-square goodness of fit

```
proc freq data = "c:/mydata/data_name";
  tables race / chisq testp=(10 10 10 70);
run;
```

## Two independent samples t-test

```
proc ttest data = "c:/mydata/data_name";
  class female;
  var write;
run;
```

## Wilcoxon-Mann-Whitney test

```
proc npar1way data = "c:/mydata/data_name" wilcoxon;
  class female;
  var write;
run;
```

## Chi-square test

```
proc freq data = "c:/mydata/data_name";
  tables schtyp*female / chisq;
run;
```

## Fisher's exact test

```
proc freq data = "c:/mydata/data_name";
  tables schtyp*race / fisher;
run;
```

## One-way ANOVA

```
proc glm data = "c:/mydata/data_name";
  class prog;
  model write = prog;
  means prog;
run;
quit;
```

## Kruskal Wallis test

```
proc npar1way data = "c:/mydata/data_name";
  class prog;
  var write;
run;
```

## Paired t-test

```
proc ttest data = "c:/mydata/data_name";
  paired write*read;
run;
```

## Wilcoxon signed rank sun test

```
data hsb2a;
  set 'c:/mydata/data_name';
  diff = read - write;
run;

proc univariate data = hsb2a;
  var diff;
run;
```

## McNemar test

```
data set1;
  input Q1correct Q2correct students;
  datalines;
  1 1 172
  0 1 6
  1 0 7
  0 0 15
run;

proc freq data=set1;
  table Q1correct*Q2correct;
  exact mcnem;
  weight students;
run;
```

## Friedman test

```
proc sort data = "c:/mydata/data_name" out=hsbsort;
  by id;
run;

proc transpose data=hsbsort out=hsblong name=rwm;
  by id;
  var read write math;
run;

proc freq data=hsblong;
  tables id*rwm*col1 / cmh2 scores=rank noprint;
run;
```

## Correlation

```
proc corr data = "c:/mydata/data_name";
  var read write;
run;
```

```
cor.test(read, write)
```

## Simple linear regression

```
proc reg data = "c:/mydata/data_name";
  model write = read / stb;
run;
quit;
```

## Non-parametric correlation

```
proc corr data = "c:/mydata/data_name" spearman;
  var read write;
run;
```

## Simple logistic regression

```
proc logistic data = "c:/mydata/data_name" desc;
  model female = read / expb;
run;
```

## Multiple regression

```
proc reg data = "c:/mydata/data_name";
  model write = female read math science socst / stb;
run;
quit;
```

## Analysis of covariance

```
proc glm data = "c:/mydata/my_data";
  class prog;
  model write = prog read;
run;
quit;
```

## One-way MANOVA

```
proc glm data = "c:/mydata/data_name";
  class prog;
  model read write math = prog;
  manova h=prog;
run;
quit;
```