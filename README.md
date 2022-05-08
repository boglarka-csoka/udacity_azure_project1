# Optimizing an ML Pipeline in Azure

## Overview
This project is part of the Udacity Azure ML Nanodegree.
In this project, we build and optimize an Azure ML pipeline using the Python SDK and a provided Scikit-learn model.
This model is then compared to an Azure AutoML run.

## Useful Resources
- [ScriptRunConfig Class](https://docs.microsoft.com/en-us/python/api/azureml-core/azureml.core.scriptrunconfig?view=azure-ml-py)
- [Configure and submit training runs](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-set-up-training-targets)
- [HyperDriveConfig Class](https://docs.microsoft.com/en-us/python/api/azureml-train-core/azureml.train.hyperdrive.hyperdriveconfig?view=azure-ml-py)
- [How to tune hyperparamters](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-tune-hyperparameters)


## Summary
This dataset contains personal data like age, marital status, etc. We seek to predict the binary y variable.
To do this, we first try to optimize the hyperparameters of the logistic regression. Then try AutoML and see what this suggests.


## Scikit-learn Pipeline
**Explain the pipeline architecture, including data, hyperparameter tuning, and classification algorithm.**
I tuned 2 hyperparameters: C and the max number of iteration. C is the inverse of the regularization strength. 
It chooses between the child runs based on the accuracy metric.The child run which has the highest accuracy will provide the needed hyperparameters for the logistic regression. Here the models have really similar primary metrics (appr. 0.9).

**What are the benefits of the parameter sampler you chose?** 
My choice is random sampling. It supports continuous and discrete parameters and also early termination. This method chooses randomly from the given parameter space.It is quite fast and get optimal results with less resource.

**What are the benefits of the early stopping policy you chose?**
My choice is Bandit policy. It helps to terminate a run when it's primary metric isn't within the slack factor of the until then most successful run. This saves time and resource.

## AutoML
It stopped because of timeout. The best model: VotingEnsemble (StandardScalerWrapper, XGBoostClassifier, ensable weight:0.143), Accuracy: 0.918. We can see explanation and metrics with plots if we open the provided link. 

## Pipeline comparison
The best models of the 2 methods gave really similar primary metrics (accuracy). Hyperparameter tuning is good if a specific model (e.g. logistic regression) is required and an expert can do it wisely. AutoML is really useful for users who are not involved deeply in the models. Overall the best model of AutoML gave a little bit better result.

## Future work
Optimizing other hyperparameters (e.g. the type of penalty) would be useful, because they can contribute to better model performance.
Choosing another primary metric for hyperparamter tuning would be better because accuracy usually has some disadvantages.

