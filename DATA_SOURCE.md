# Iris multiclass practice

This local CSV comes from `sklearn.datasets.load_iris(as_frame=True)` in scikit-learn 1.9.0. It contains 150 real flower observations with 50 examples of each species: setosa, versicolor, and virginica. One row describes one flower. The four measurements are sepal length, sepal width, petal length, and petal width, all in centimeters.

Sources: [scikit-learn load_iris documentation](https://scikit-learn.org/1.9/modules/generated/sklearn.datasets.load_iris.html) and [UCI Iris](https://archive.ics.uci.edu/dataset/53/iris), R. A. Fisher, donated by Michael Marshall. DOI: https://doi.org/10.24432/C56C76. UCI license: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Accessed October 16, 2026.

Course changes: renamed measurement columns to short names ending in `_cm`, replaced numeric target codes with their species names, and exported a CSV. All 150 rows remain. No values were invented. scikit-learn documents corrections to two records relative to some older versions of Iris, so compare against the scikit-learn version used here.

Task: classify an already measured flower into one of these three known species. This is supervised classification because training labels are known. All four numerical features are available before classification. There are no categorical inputs or missing values in this copy.

Requirements: use all four measurements as X and `species` as y. Split with `test_size=0.25`, `random_state=9`, `stratify=y`. Use median imputation followed by StandardScaler and LogisticRegression(max_iter=1000) in one Pipeline. Fit only on training data. Fit a DummyClassifier(strategy="most_frequent") on the same training rows. Report accuracy and a confusion matrix in the order setosa, versicolor, virginica. Calculate precision and recall separately for each species using `average=None` and this same labels list, with `zero_division=0`. The practice goal is accuracy greater than baseline accuracy. No threshold tuning or model comparison is required.

Limitations: this is a small, balanced historical teaching dataset with only three species. Strong performance does not show readiness for other species, measurement tools, or growing conditions. The known-label requirement distinguishes this exercise from discovering groups through clustering.
