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

Unfortunately I haven't got results, so I can't answer this question yet.

## Scikit-learn Pipeline
**Explain the pipeline architecture, including data, hyperparameter tuning, and classification algorithm.**

**What are the benefits of the parameter sampler you chose?** My choice is random sampling. It is quite fast and get optimal results with less resource.

**What are the benefits of the early stopping policy you chose?** My choice is Bandit policy. It helps to terminate a model when it's not close to the until then best model. This saves time and resource.

## AutoML


## Pipeline comparison


## Future work


## Proof of cluster clean up

**Image of cluster marked for deletion** I don't know how to attach an image here, but I deleted both clusters which I created.
