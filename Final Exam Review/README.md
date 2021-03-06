# Questions to Review

## Homework 2

### Theory 2

I collect a set of data (n = 100 observations) containing a single predictor and a quantitative response. I then fit a linear regression model to the data, as well as a separate cubic regression, i.e., Y = β0 + β1X + β2X2 + β3X3 + ε.

(a) Suppose that the true relationship between X and Y is linear, i.e. Y = β0 + β1X + ε. Consider the training residual sum of squares (RSS) for the linear regression (noticing that MSE = SSE/n in this case), and also the training RSS for the cubic regression. Would we expect one to be lower than the other, would we expect them to be the same, or is there not enough information to tell? Justify your answer.

(b) Answer (a) using test rather than training RSS.

(c) Suppose that the true relationship between X and Y is not linear, but we don’t know how far it is from linear. Consider the training RSS for the linear regression, and also the training RSS for the cubic regression. Would we expect one to be lower than the other, would we expect them to be the same, or is there not enough information to tell? Justify your answer.

(d) Answer (c) using test rather than training RSS.

### Computation 2

This question should be answered using the `Carseats` data set.

(a) Fit a multiple regression model to predict `Sales` using `Price`, `Urban`, and `US`.

(b) Provide an interpretation of each coefficient in the model.

(c) Write out the model in equation form, being careful to handle the qualitative variables properly.

(d) For which of the predictors can you reject the null hypothesis H0 : βj = 0?

(e) On the basis of your response to the previous question, fit a smaller model that only uses the predictors for which there is evidence of association with the outcome.

(f) How well do the models in (a) and (e) fit the data?

(g) Using the model from (e), obtain 95% confidence intervals for the coefficient(s).

(h) Using the leave-one-out cross-validation and 5-fold cross-validation techniques to compare the perfor- mance of models in (a) and (e). What can you tell from (f) and (h)?

## Homework 3

### Theory 1

Consider the ridge regression with tuning parameter λ = 0 and the constrained version of LASSO with tuning parameter s >= 0. As λ and s increase from 0 respectively, indicate which of the following is correct for: 

(a) training RSS, (b) test RSS, (c) variance, and (d) (squared) bias. Justify your answer.

(i) Increase initially, and then eventually start decreasing in an inverted U shape. 

(ii) Decrease initially, and then eventually start increasing in a U shape.

(iii) Steadily increase. 

(iv) Steadily decrease. 

(v) Remain constant.

### Theory 2

### Computation 1

## Homework 4

### Theory 1

**Are the following sentences about PCR and PLS true or false? Briefly justify your answer.**

**(i) Both PCR and PLS come up with orthogonal features.**

True. The reason follows the optimization formulation of PCR and the orthogonality arguments of PLS.

**(ii) Let Zp1q, Zp2q,  ̈  ̈  ̈ , Zppq be the features obtained by PLS. For an intermediate k ă p, we fit a regression model Y on Zp1q, Zp2q,  ̈  ̈  ̈ , Zpkq, and obtain a predicted response Yˆ pkq on the training
set. Then Yˆ pkq is orthogonal to the subsequent features Zpk`1q, Zpk`2q,  ̈  ̈  ̈ , Zppq. Therefore, to compute Yˆ pk`1q (the predicted response based on Zp1q, Zp2q,  ̈  ̈  ̈ , Zpkq, Zpk`1q), we can first regress Y on Zpk`1q only and obtain Yˆ pZpk`1qq (the predicted response based on Zpk`1q only), and then let
Yˆ pk`1q Ð Yˆ pkq ` Yˆ pZpk`1qq.**

True. They are orthogonal. As a result from the linear model, if the covariates are orthogonal (hence the design matrix is orthogonal), then the coefficient estimates are independent of each other. Namely, adding another term to the working model with the covariates wouldn't alter the coefficient estimates for the original covariates.

**(iii) The first feature from PLS is more predictive towards the response in the training set than that from PCR.**

False. It's anticipated that the first feature (or the first *k* features) from PLS are more predictive than that from PCR, since PLS tries to capture the correlations between the covariates and the response as much as possible whereas PCR does not. However, the predictivity of the PLS features is indeterminante due to the following perspectives: 

- Perspective I: Since the correlation criteria is "partial" towards each covariate, but not "jointly" towards the constructed feature, the result should be indeterminate.
- Perspective II: As can be seen from the optimization formulation, each PLS feature is chosen to maximize a compromised measurement in its varianc and correlation with the response, while the training errors (or R squared) only depend on the correlations of features with the response, the result should be indeterminate.

**(iv) In the procedures of constructing features from PCR and PLS, the earlier a feature is included in the regression model, the faster the training R squared increases.**

False. The procedure of PCR is irrelevant to the response vector and so it is irrelevant tot he fitted consequences, includign R squared. Similarly, PLS follows the same rule.

**(v) Using the features from PCR and PLS has lower training errors and test errors than those of the original model.**

False. Both PCR and PLS have higher training RSSs, unless we use all the features in PCR and PLS (leads to a saturated model). Since both the parsimonious (not including all features) PCR and PLS form sub-models of the original linear model, the original linear model would have the least training RSS (due to least square). However, if all features are included in PCR and PLS, the resulting model is equivalent to the original linear model, hence it would give the same training RSS.

In terms of test errors, we anticipate that as the number of features from PCR or PLS increases (up to the saturated model), the test RSS would decrease first and then increase eventually due to the bias-variance tradeoff. When the number of features is 0, PCR and PLS given the simplest model with lowest variance and highest bias. As the number of features increases, PCR and PLS tend to give a model more similar to the (saturated) linear model. In the extreme case, there might be overfitting issue unless the saturated linear model is well- or under-specified. Therefore, the variance would increase whereas the bias would decrease overtime. And the test error would behave as a U shape as the number of features increase.

### Theory 3

**Suppose we collect data for a group of students in a statistics class with variables X1 = hours studied, X2 = undergrad GPA and Y = receive an A. We fit a logistic regression and produce estimated coefficient, β^0 = -6, βˆ1 = 0.05, βˆ2 = 1.**

(a) Provide an interpretation of each coefficient in the model. Note that β^0 corresponds to an additional intercept in the model.

(b) Estimate the probability that a student whose studies for a 40 hours and has an undergrad GPA of 3.5 gets an A in the class.

(c) How many hours would the student in part (b) need to study to have a 50% chance of getting an A in the class?

### Theory 4

**(a) If the Bayes decision boundary is linear, do we expect LDA or QDA to perform better on the training set? On the test set?**

QDA will probably perform better on the training set because of the high flexibility, thus leading to a closer fit (lower bias). However, on the test set, we cannot make any further assumptions unless we know more about about the nature of the relationship of the predictors and the response. Even though the Bayes decision boundary may be linear, the underlying distributional relationships may not be Gaussian. Therefore, neither LDA nor QDA fits into the framework.

**(b) If the Bayes decision boundary is nonlinear, do we expect LDA or QDA to perform better on the training set? On the test set?**

Nonlinearity does not imply a quadratic boundary and we do not know if this setting holds up the Gaussian assumptison of QDA for the test set.

**(c) In general, as the sample size *n* increases, do we expect the test prediction accuracy of QDA relative to LDA to improve, decline, or be unchanged? Why?**

We would expect the accuracy of QDA to improve relative to LDA to improve as the sample size *n* increases, because a more flexible method will yield a less biased model while the variance from the training set would be vanishing as n approaches infinity.

**(d) True or False: Even if the Bayes decision boundary for a given problem is linear, we will probably achieve a superior test error test error rate using QDA rather than LDA because QDA is flexible enough to model a linear decision boundary. Justify your answer.**

False. QDA could overfit the model and lead to a higher test error. It would lead to a higher variance from the training set, yielding a higher test error rate than LDA.

### Computation 1

## Homework 5

### Theory 2

### Theory 3

### Computation 1

## Homework 6

### Theory 1

**Are the following statements True or False? Briefly justify your answer.**

**(i) In regresion tree problem, the recursive binary splitting can be formulated as a generalized forward stepwise regression algorithm. However, the legitimate entering variable candidates at each forward regression step depends on the current predictors.**

True. One-step binary splitting is equivalent to one-step forward regression. 

**(ii) A decision tree permits a partition X1X2 >= 3**

False. Decision trees only permit rectangles

**(iii) Since two bootstrap samples are iid from a given dataset, the same statistics (e.g., sample means) computed out of them are iid as well.**

False. The bootstrap samples are iid *conditional* on the given dataset. If the dataset is considered as a random sample from the population, then the bootstrap samples out of it are dependent with each other, so as the statistics computed out of them. Distributions of bootstrap statistics are identical.

**(iv) The out-of-bag (OOB) error underestimates the test error of the bagging model since it "overuses" the training sample.**

False. A bag is independent of the OOB sample points even though the dataset is considered as random. Therefore, the prediction of the model based on the bags not including a held-out sample point. Generally, the OOB error is generally larger than (overestimating) the actual prediction error.

**(v) When the number of variables is large, but the fraction of relevant variables is small, random forests are likely to perform poorly with small *m*, the number of predictors in each tree.**

True. If the relevant variables are rare relative to the number of predictors in a component tree, then the chance that important predictors are included is quite small. This is, there would be too many poorly fitted components trees in the forest.

### Theory 3

### Computation 1 

### Computation 2

## Homework 7 

### Theory 1

### Theory 3

### Computation 2
