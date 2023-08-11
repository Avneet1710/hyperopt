### Hyperopt

Hyperopt is a Python library for serial and parallel optimization over awkward search spaces, which may include real-valued, discrete, and conditional dimensions. Use tpe.suggest for itterate on the grid space.

### How to define space

space takes a dictionary as an input and use of hp.<distribution> to supply the values it can take. Following is the best way to define the grid as suggested by the Databricks:

| Hyperparameter Type	| Suggested Hyperopt range |
|:--------------------|-------------------------:|
| Maximum depth, number of trees, max 'bins' in Spark ML decision trees	| hp.quniform with min >= 1 |
| Learning rate	hp.loguniform with | max = 0 |
| Regularization strength	| hp.uniform with min = 0 or hp.loguniform |
| Ratios or fractions, like Elastic net ratio	| hp.uniform with min = 0, max = 1 |
| Shrinkage factors like eta in xgboost	| hp.uniform with min = 0, max = 1 |
| Loss criterion in decision trees (ex: gini vs entropy) | hp.choice |
| Activation function (e.g. ReLU vs leaky ReLU) |	hp.choice |
| Optimizer (e.g. Adam vs SGD)	| hp.choice |
| Neural net layer width, embedding size	| hp.quniform with min >>= 1 |
