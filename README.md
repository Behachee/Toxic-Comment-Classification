# Toxic-Comment-Classification

## Overview
Welcome to the Toxic comment classification challenge!

Automated assessment of user-generated text, such as identifying toxic comments, serves as a crucial tool for managing the vast volume of online content. Regrettably, previous studies have revealed that these classifiers for toxicity often inherit biases from their training data.

The challenge is cast as a subpopulation shift problem. where distinct demographic identities represent these subpopulations. Our aim is to achieve high performance across all these subpopulations, rather than only focusing on the average performance across them. The emphasis is on reducing biases related to comments referencing specific demographic groups, rather than comments authored by individuals from those particular demographics.

## Description
This competition aims to revolutionise the landscape of comment classification within online discourse. Participants will dive into the task of determining the toxicity of comments posted on various online articles. The ultimate goal is to build models that not only accurately identify toxic comments but also demonstrate robustness across diverse demographic subpopulations.

The primary objective of this challenge is to develop innovative solutions that mitigate biases inherent in comments mentioning specific demographic identities. Participants are tasked with crafting models that excel in fairness and accuracy across these demographic subpopulations, aiming for superior performance beyond mere overall averages.

Join us in this pursuit of fostering fairness and impartiality in comment classification algorithms, thereby shaping a more inclusive and respectful online environment.

## Evaluation
Submissions are evaluated on the Worst-group accuracy. To study the bias of annotating comments that mentions demographic groups as toxic, the models performance will be evaluated by
1) Each of the 8 demographic identities will be separated into 2 groups by toxicity – for example, separate black into black, toxic and black, not toxic;
2) Measure the accuracies of these 8 × 2 = 16 groups and use the lowest accuracy as the final evaluation of the model.

This metric consists of calculating both the sensitivity and specificity of the classifier across each demographic identity, and then highlighting the lower metric among the two across all domains. Strong performance on the group with the lowest accuracy suggests that the model refrains from relying on demographic identity as an indicator of toxic comments.

## Submission File
For each ID in the test set, you must predict a probability for the pred variable. It is very important for the file to have the correct format, and to pay attention to the ID of the prediction (see baseline notebook). The file should contain a header and have the following format:

## Dataset Description
There are 5 files provided: 3 .csv files for the data and 2 csv files as the labels, across the training, validation and test sets (only the data on the test set). Keep in mind that only 30% of the test set is public (i.e. the score you see on the leaderboard before the deadline), whereas the final leaderboard will be made on the remaining 70%. We also provide you with a baseline.ipynb which provides you with some useful code for datasets, training, and submission preparation.

Files
- test_x.csv
- train_x.csv
- train_y.csv
- val_x.csv
- val_y.csv
- baseline.ipynb

Columns
The first 8 columns represent the 8 demographic groups which we are considering in the computation of the metric. The y column represents the label.

- male
- female
- LGBTQ
- christian
- muslim
- other_religions
- black
- white
- identity_any
- severe_toxicity
- obscene
- threat
- insult
- identity_attack
- sexual_explicit
- y --> This is the target variable
from_source_domain
