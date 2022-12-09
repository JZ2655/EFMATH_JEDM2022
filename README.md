# EFMATH_JEDM2022
# description of files

- “Start” folder contains 10 example clips 
- the r and rmd version of feature extraction are identical. Running either one will output a csv file with a filename that ends with today’s date. This is the feature file used in the model
- the two csv files (top 2 strategies and keywordList are called in the feature extraction.r /(.rmd) file
- use “run detector.ipynb” to import the model and make predictions. update the filename of the features
- “building models” folder contains original dataset used to build the model, where the sav files are created from

# note
Update the “keywordList.csv” and “df_Top2strategiesSelected.csv” periodically. The feature extraction code will break if it cannot find the name of a problem item in the files. 

# library/package version
Python version 3.8.8
R version 4.1.1

pandas (1.0.5)
numpy (1.20.1)
sklearn (0.24.1)
xgboost (1.5.0)
rpy2 (3.5.4)

import pickle
import random

from xgboost import XGBClassifier
from sklearn import preprocessing
from sklearn.model_selection import GroupKFold, train_test_split
from sklearn.metrics import classification_report, roc_curve, roc_auc_score, confusion_matrix, accuracy_score, f1_score, cohen_kappa_score
