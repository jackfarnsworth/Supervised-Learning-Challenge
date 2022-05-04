# Supervised-Learning-Challenge
This is a project for Georgia Tech's Data Analytics Bootcamp. Credit Risk Evaluator contains a jupyter notebook using sklearn to use 2019 credit risk dataframes to predict a future datasets outcomes.

### Predictions

Predicting outcomes prior to scaling almost always favors random sampling. The fundamental idea of creating a logistic regression in N dimensions without scaling is frankly guaranteed for difficulty. In our case we have plenty of non-normalized values on different orders of magnitude which will throw off our analysis. Namely we have loan amounts (10^5 typically), interest rates (10^1), annual income (10^6) and installment (10^4) among others. Whenever we have such disparately valued features, a logistic regression will tend towards the larger amounts.

On the other hand, if we create decision trees from randomly sampled features, the disparate nature of the data will be largely minimized. Decision trees in general are less prone to vast differences in magnitude as they don't tend to  ualify  uestions of magnitude i.e. they make their decisions one feature at a time rather than taking them in aggregate. With data that exists on orders of magnitude as different as ours, I would expect a random tree classifier to perform much better.

After scaling what I would expect to see is the regression tests to perform significantly better (as our orders of magnitude are reduced to be on a scalem from -2 to 2) and our random forest classifer to be realtively unchanged as a decision tree is making decisions on a feature by feature basis, so scaling of features should not matter.

### Post-Analysis

As expected, our linear analysis saw great improvements from scaling the data (.5 -> .76) whereas our random forest classifier saw a modest increase in performance, though this potentially due to the random nature of sampling (.63 -> .64). Scaling your data has no impact on random forest classifiers as they are already making decisions largely on a feature to feature basis, but scaling data for linear regressions, where changes in scale have massive impact on their relative weights, results in a significantly better predictive model.
