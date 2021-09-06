# kTSP-predicting-age-feature-selection
# Overview
Ensemble combined with LDA is effective in predicting age based on gene expression data. However, this method is prone to batch problem. The batch problem may caused by the different techniques in breeding cells that lead to difference in the mean gene expression level of cells between batches.

kTSP is a potential solution to the batch problem because it uses the relative gene expression level rather than the raw qualititative data. It also involves significant less amount of features, improving both the speed of training and predicting and the interpretability of the features.

The data used for training in this notebook are all from gene_labelled_data.csv

# File structure
-kTSP.ipynb: kTSP classifier and feature selection\
This notebook completes three tasks: 10-fold CV repetead 3 times for predicting age using kTSP classifer on entire data; feature selection of gene pairs by kTSP algorithm to use in ensemble; and predict age on data reserved from feature selection using kTSP classifier. It generates a new csv file "binary_gene_labels" that contains a binary matrix of the gene expression data. The row of the generated file is each person, and the column is each TSP that aims to reduce batch problem by transforming raw expression data to relative expression level.

-Train your own predictor on your data.ipynb\
This notebook loads gene expression data and performs prediction on a chosen method (i.e. LDA, KNN, Random Forest, etc.) in customized ensemble. It generalizes a graph to visualize the performance of the model.

-age_predictors.py\
This file contains codes that implement classes of ensembles using different predicting methods.

-gene_labelled_data.csv\
The orignial gene expression used for feature selection and generation of the new csv file.

# Requirements on environment
rpy2 version: 3.4.5
R version: 4.1.0
multiClassPairs version: 0.4.3
switchBox version: 1.28.0
python version: 3.8.8
scikit-learn version: 0.24.1
seaborn version: 0.11.1
