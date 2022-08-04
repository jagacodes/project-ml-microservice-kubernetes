[![CircleCI](https://dl.circleci.com/status-badge/img/gh/jagacodes/project-ml-microservice-kubernetes/tree/master.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/jagacodes/project-ml-microservice-kubernetes/tree/master)

## Project Overview

The PROJECTML project contains a Machine Learning Microservice, built on **Scikit-Learn**. It contains a model that predicts house prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). 

## What does this project do?

- Run a docker container
- Upload container into a public registry (hub.docker.com)
- Run the deployed application in a Kubernetes cluster
- Integrate with CircleCI to test and lint the application code and DockerFile for continuous integration

## Requirements
 - Python 3.7

## START HERE

### First Step
- Fork this repo and clone it to your local workstation or Developement Environment

### Second Step: Install dependencies
- Note the MakeFile in the current dir that enables you setup tasks like setting up your environment, testing and linting
- Set up the environment by running `make setup`. This will create a virtual environment in your home directory called `.devops`
- Install dependencies by running `make install`
- Lint application (requires hadolint)

### Third Step: Run Docker container
- Run the application on docker by calling `./run_docker.sh`

### Fourth Step: Upload to Docker Hub
- In the `./upload_docker.sh` file, edit the dockerpath to your built docker hub repository and change the docker username to a personalized one (or leave it as is, to use the public jagacodes/projectml:v1.0)
- To upload to docker hub, run `./upload_docker.sh`

### Fifth Step: Kubernetes deployment
- To deploy to kubernetes, run `./run_kubernetes.sh`