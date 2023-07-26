## Pre-requisites
1. Create a Resource group
2. Create an Azure Machine Learning Service
3. Install az cli - https://learn.microsoft.com/en-us/cli/azure/install-azure-cli
4. Install ml package in az cli - https://learn.microsoft.com/en-us/azure/machine-learning/how-to-configure-cli?view=azureml-api-2&tabs=public
5. az login
6. Install VS Code
7. Install Azure Machine Learning extension for VS Code

## Exercise 1 - Create compute instance using Portal/CLI/VSCode
1. Log into the AML Workspace
2. Create your compute instance by completing the 00-create-compute-instance.yml file. Use the `az ml compute create --file 01-create-compute-instance.yml` command. Additional params - https://learn.microsoft.com/en-gb/azure/machine-learning/reference-yaml-compute-instance?view=azureml-api-2

## Exercise 2 - Uploading data and working with datasets using Portal/CLI/VSCode
1. Populate the MLTable file with instructions on how to read the csv in the ./data folder
2. Create a data asset by completing the 01-create-data-asset.yml file. Use `az ml data create --path ./data --name <DATA ASSET NAME> --version <VERSION> --type mltable` or `az ml data create --file 02-create-data-asset.yml`

## Exercise 3 - Creating environments using Portal/CLI/VS Code
1. Explore and edit the workstation_env.yaml file under the conda_yamls directory
2. Create an environment by completing the 02-create-environment.yml file, Use `az ml environment create --file 03-create-environment.yml`

## Exercise 4 - Explore using notebooks/VS code
1. Author/execute the notebook using the Portal/VS Code

## Exercise 5 - Create compute cluster
Same as exercise 1

## Exercise 5 - Train a model
1. Explore and edit the train-model.yml file
2. Create/submit a job using CLI. `az ml job create --file 05-train-model.yml`

## Exercise 6 - Monitor the job and register the model
1. `az ml job show -n $run_id --web`
2. `az ml model create -n sklearn-iris-example -v 1 -p runs:/$run_id/model --type mlflow_model`

## Exercise 7 - Create endpoint
1. Explore and edit the create-endpoint.yml file
2. Create an endpoint using CLI. `az ml endpoint create --file 06-create-endpoint.yml`

## Exercise 8 - Create endpoint
1. Explore and edit the create-deployment.yml file
2. Create an deployment using CLI. `az ml endpoint create --file 07-create-deployment.yml`