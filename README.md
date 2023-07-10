
# Appliance Classification

This repository contains the Jupyter notebook (`NILM classification.ipynb`) used in the conference paper ["Designing a Machine Learning based Non-intrusive Load Monitoring Classifier"](https://www.researchgate.net/profile/Carolina-Fortuna/publication/355105512_Designing_a_Machine_Learning_based_Non-intrusive_Load_Monitoring_Classifier/links/615dca43fbd5153f47e93617/Designing-a-Machine-Learning-based-Non-intrusive-Load-Monitoring-Classifier.pdf). 

## Citation

If you use our code or results in your research, please cite:

OGRIZEK, Leo, BERTALANIČ, Blaž, CERAR, Gregor, MEŽA, Marko, FORTUNA, Carolina. Designing a machine learning based non-intrusive load monitoring classifier. V: ŽEMVA, Andrej (ur.), TROST, Andrej (ur.). Zbornik tridesete mednarodne Elektrotehniške in računalniške konference ERK 2021 = Proceedings of the 30th International Electrotechnical and Computer Science Conference ERK 2021 : Portorož, Slovenija, 20. - 21. september 2021.

## Setup

This notebook is made for use in Google Colab, which is the recommended environment to run it. It can also be used in any Jupyter environment given the dependencies are installed:

- h5py
- numpy
- pandas
- scipy
- matplotlib
- sklearn
- imblearn

You can install these modules using pip:

```bash
pip install h5py numpy pandas scipy matplotlib sklearn imbalanced-learn
```

## Overview

The notebook is structured into five sections:

1. **Data preprocessing and best result highlights:** This section demonstrates the best performing model and provides an overview of the data preprocessing steps. The models are trained on the UK-DALE dataset.

2. **Effects of feature selection:** This section compares the performance of a SVM classifier on various feature sets.

3. **Effects of scaling:** This section compares the performance of various classifiers on scaled vs. non-scaled data.

4. **Effects of algorithm optimisation:** This section compares the performance of various algorithms with default and optimised hyperparameters.

5. **Experiments with auto ML:** This section contains a test of scikit-learn's auto machine learning algorithms.

## Usage

To use this notebook, run the cells in order. The configuration is already set up as it was for the paper.
