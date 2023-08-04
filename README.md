# Neural Network Model Report: Predicting Success When Providing Funding to Organizations

## Purpose

The purpose of this analysis is to create a machine learning model than can accurately predict if an organization/project will be successful after receiving funding from Alphabet Soup.

## Preparation

* The target variable is the "IS_SUCCESSFUL" column which contains a label of either 0 or 1 (binary).
* The feature variables are the columns "APPLICATION_TYPE", "AFFILIATION", "CLASSIFICATION", "USE_CASE", "ORGANIZATION", "STATUS", "INCOME_AMT", "SPECIAL_CONSIDERATIONS", and "ASK_AMT".
* The "EIN" and "NAME" columns are removed from the input data because they are neither targets nor features.

## Model Summaries

### Model 1 - Accuracy: 0.638, Loss: 1.308

| Layer    | Neurons | Activation |
| -------- | ------- | ---------- |
| First    | 43      | relu       |
| Second   | 20      | relu       |
| Output   | 1       | tanh       |

### Model 2 - Accuracy: 0.727, Loss: 0.566

| Layer    | Neurons | Activation |
| -------- | ------- | ---------- |
| First    | 100     | relu       |
| Second   | 50      | tanh       |
| Third    | 25      | tanh       |
| Output   | 1       | tanh       |

### Model 3 - Accuracy: 0.726, Loss: 0.554 (Auto Optimizer/Keras Tuner Model)

| Layer    | Neurons | Activation |
| -------- | ------- | ---------- |
| First    | 41      | tanh       |
| Second   | 23      | tanh       |
| Third    | 31      | tanh       |
| Fourth   | 5       | tanh       |
| Fifth    | 37      | tanh       |
| Sixth    | 19      | tanh       |
| Output   | 1       | sigmoid    |

## Model Overview

This project was unable to achieve the target model performance of 0.75 accuracy.

Despite taking steps to increase the model performance like increasing the number of hidden layers, increasing the number of neurons per layer, and changing the type of activation function of each layer, the results did not improve beyond ~0.72 accuracy.

Even the auto optimizer was not able to improve the accuracy or lower the loss by a significant amount.

## Summary & Recommendation

The overall results of this deep learning model are underwhelming. Manipulating the model paramenters did not improve the results. This may indicate that the dataset is unsuitable for this model or that the data needs to be cleaned or processed further.

For example, the INCOME_AMT column would theoretically have floats or integers. However, this column is filled with numbers of different formats (including abbreviations and number ranges).

The recommendation of this project is to continue with the current model if it satisfies the business requirements of Alphabet Soup's executives. If the accuracy and loss results are not acceptable, the data should be re-examined, cleaned, and transformed until it is more suitable for this deep learning model (and can potentially produce better results for accuracy and loss).


## A different Model
Given more time and computer processing resources, the model could be expanded to use hundreds of neurons and hundreds of epochs to see if that can improve the results.

In addition, since the models in this project relied heavily on tanh, a different model could be created so that more layers use relu and sigmoid activation functions instead of tanh.

Finally, a different model could be built on a non-tensorflow library such as MATLAB and PyTorch.