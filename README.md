# ApplianceClassification

### Citation

The jupyter notebook in this repository (NILM classification.ipynb) contains the code and results used in the conference paper ["Designing a Machine Learning based Non-intrusive Load Monitoring Classifier"](https://www.researchgate.net/profile/Carolina-Fortuna/publication/355105512_Designing_a_Machine_Learning_based_Non-intrusive_Load_Monitoring_Classifier/links/615dca43fbd5153f47e93617/Designing-a-Machine-Learning-based-Non-intrusive-Load-Monitoring-Classifier.pdf). If you are using our code or results in your own research please cite

OGRIZEK, Leo, BERTALANIČ, Blaž, CERAR, Gregor, MEŽA, Marko, FORTUNA, Carolina. Designing a machine learning based non-intrusive load monitoring classifier. V: ŽEMVA, Andrej (ur.), TROST, Andrej (ur.). Zbornik tridesete mednarodne Elektrotehniške in računalniške konference ERK 2021 = Proceedings of the 30th International Electrotechnical and Computer Science Conference ERK 2021 : Portorož, Slovenija, 20. - 21. september 2021.

### Overview

The notebook is structured into 5 segments. The first segment contains synthetic feature creration and examples of best performing code segments. The 2nd contains detailed results depicting the importance of feature selection, which was published in the paper. The 3rd section overviews the effects of scaling of data on model performance. All results used in the paper came from scaled data, which has proven superior. Results from the 3rd section were not directly published. 4th section compares various algorithms with default and optimised hyperparameters, results from this section were published in the paper. Last section is a test of scikit learn's implementation of auto machine learning, where the right model and its hyperparameters are chosen automatically.

### Section 1: Data preprocessing and best result highlights

The models in this notebook are trained on UK-DALE, a publicly available dataset containing measurements of power consumption of 9 common household appliances (computer monitor, laptop computer, television, washer dryer, microwave, boiler, toaster, kettle, fridge). The dataset contains 300 samples with 600 measurements per device. One example sample of each appliance is also shown in this section. A variety of properties is calculated for every sample to be used as synthetic features in the classification. The full list of used features is: mean and its square, skew and its square, kurtosis, standard deviation and its square, minimum, maximum, peak-to-peak, variance, sum of all data points, median, how many times the coefficient of the line connecting neighbouring points changes sign within a sample and the sum of all differences between neighbouring points in a sample. The last part of this section contains a demonstration of the best performing model both in a confusion matrix and as an average of a large number of iterations. Optimised versions of every tested classifier are appended in the end.

### Section 2: Effects of feature selection

Here a comparison of classificaton performance on various feature sets can be found. A SVM was chosen as a test classifier, as it performs the best on this dataset. This section compares performance on raw data and on various arbitrarily chosen combinations of synthetic features. Best performing feature set was chosen by elimination. First every feature was used at once, then a single feature was removed. If its elimination improved the performance it was left out. All results are shown in 5 classification reports, 1 for every fold in 5 fold cross validation used to decrease performance evaluation inaccuracies do to random data splits.

### Section 3: Effects of scaling

This section overviews the classification performance on scaled vs. non scaled data. All data was scaled using scikit learn standard scaler. Comparisons were made on all classifier types tested in the 4th section: SVM, MLP, K nearest neighbours, logistic regression and random forest. Effects of scaling were compared on the best performing feature set from section 2.

### Section 4: Effects of algorithm optimisation

This section contains the comparison between various algorithms with default and optimised hyperparameters. Tested algorithms were SVM, MLP, K nearest neighbours, logistic regression and random forest. Optimisation was made using a grid search algorithm. For SVM the optimised parameters were the kernel and regularization parameter. For MLP the optimised parameters were the initial learning rate and learning rate schedule. A few tests were made on effects of changing the hidden layers. For K nearest neighbours the optimised parameter was the number of neighbours checked. For logistic regression the optimised parameters were the solver and the regularization parameter. For random forest the optimised parameter was the number of estimators.

### Section 5: Experiments with auto ML

This section contains a test of scikit learn auto machine learning algorithms, which determines the best classifier for a given dataset automatically. The model will train for 2 hours by default. 