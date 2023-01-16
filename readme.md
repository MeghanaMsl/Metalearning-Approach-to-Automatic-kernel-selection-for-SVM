# A Meta-learning approach to automatic kernel selection for Support Vector Machines

---

## Overview
This project aims at solving the dilemma involved in choosing a kernel for Support Vector Machines.
The kernel selection is usually done using trial and error methods that impact the accuracy of the model when not correctly chosen.

To Address this issue, I use the Meta-learning approach to Automatically select the kernels. I seek to understand the best suitable kernel for a given classification problem using the spatial-statistical characteristics of the data.

## Dataset
The project was done using 7 classification datasets which belong to Medical, Financial, Chemical and Phytology domains taken from the UCI Machine Learning repository.

P.S: The accuracy of the final meta-learning rule increases with the number of datasets we use for training the meta-classifier.

## Implementation
The steps involved in calculation of the meta-features and the final meta-learning rule that is required to automatically select an SVM kernel can be summarized in five steps shown below:

**Step 1**: Calculate the Inter quartile range and Median for every attribute of the dataset.

**Step 2**: Calculate a variogram based on the IQR and Median values extracted from the
attributes of a dataset.

**Step 3**: Fetch the range, sill values of the variogram and store as meta-features for the
dataset.

**Step 4**: Select the SVM kernel (Linear, Polynomial, RBF) with the highest accuracy as the target value for the meta-learner.

**Step 5***: Generate the rule for automatic kernel selection by passing the generated
metadata to the meta-learner (Decision tree).

*Note: Steps 1 to 4 are repeated for all the datasets before step 5 is performed.

## Result
The final rule that has been created using our Decision tree meta-classifier is shown below:

![Alt text](rule.jpg?raw=true "Results")

The meta-features values on which the decision tree classifier was trained are as follows:
![Alt text](result.png?raw=true "Results")

In this project the abstraction of base statistical parameters has led to a more robust and simpler rule for SVM kernel selection. The rule can also be further refined by considering large number of datasets for the study.

This project is an attempt to experiment with spatial-statistical functions to derive meta-features for the dataset and understand its characteristics without overfitting the rule for a particular domain/ dataset category. It still holds scope for a lot of improvement and future research in terms of choosing different base statistical parameters or trying out different variogram models and hyperparameters.