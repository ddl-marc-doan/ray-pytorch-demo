# Training Models with PyTorch and Ray

This repo contains a few Jupyter Notebooks that illustrate how you can use existing (or new!) PyTorch code within an on-demand Ray cluster in Domino. The demo for this repository uses the Domino Standard Environment (DSE) 5.10, and the Ray (2.9.0) cluster image that's vendored with Domino 5.10

Some notes on the notebooks:

[text](Ray-Lab01.ipynb) - This is a notebook showing an example of hyperparameter tuning in a Ray cluster.

[text](convert_existing_pytorch_code_to_ray_train.ipynb) - This notebook takes the tutorial code for PyTorch, and shows how it can be used with minimal changes within a Ray cluster.

[text](ray_tune_hyperparameter_search.ipynb) - This notebook shows integration with hyperparameter tuning on Ray and how to record the results in an MLFlow experiment.

## Requirements

There are two requirements files: `requirements.txt` and `requirements-ray-environment.txt`. Both can be used for installing required libraries on a Ray Environment within Domino - or you can dynamically load the `requirements.txt` libraries into your Ray cluster via a runtime_env directive (this is illustrated in the second notebook).

## Considerations

This code is designed to be used within a Domino deployment. It assumes that you will have access to a Domino Dataset within your project. The dataset mount point is not hard-coded: it uses Domino-specific environment variables to allow for easier code reuse.