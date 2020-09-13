[![CircleCI](https://circleci.com/gh/Amamgbu/predictionapp.svg?style=svg)](https://circleci.com/gh/Amamgbu/predictionapp)
## Project Overview
Predictionapp is a project centred around operationalizing a machine learning microservice using Kubernetes, an  open-source system for automating deployment, scaling, and management of containerized applications. In this project, a pre-trained model designed to predict Boston housing prices gotten from the [Boston Kaggle dataset](https://www.kaggle.com/c/boston-housing) is used. The pre-trained model is wrapped in a Flask app and predictions are made from API calls made to the app. The Flask app is further containerized using Docker and Kubernetes. Automated tests are made using CircleCI.

## :page_with_curl:  _Project Instructions_

**1)** Open your terminal and clone the repo using the following:
> __`git clone https://github.com/Amamgbu/predictionapp.git`__

**2)** Navigate into directory:
__`cd predictionapp`__

**3)** Make sure python is already installed in your PC. If not already installed, download latest version here: [python](https://www.python.org/)

**4)** Create a virtual environment and activate by running the following command:
__`make setup`__

**5)** In order to install project dependencies, run the following:
__`make install`__

**6)** Lint files to test for syntax correctness using command:
__`make lint`__

**7)** In order to build docker image and start app, run the following command:
__`./run_docker.sh`__

**8)** In order to test app by making predictions, run the command:
__`./make_prediction.sh`__

Once predictions are made successfully, the following processes are followed:

**9)** Edit upload_docker.sh and change dockerpath to contain ID(username) of your docker container. After this is done, run the following:
__`./upload_docker.sh`__

**10)** The following command is run in order to run the service in a Kubernetes cluster. Ensure Minikube and Kubernetes is installed on your local machine. Follow this tutorial for more info on how to achieve this on Ubuntu: [Kubernetes Tutorial:Ubuntu] (https://phoenixnap.com/kb/install-minikube-on-ubuntu). After install, edit dockerpath on run_kubernetes.sh and replace with your DockerID.
__`./run_kubernetes.sh`__

**11)** You can test the app deployed by making predictions. Make sure port forwarding is successful.
__`./make_prediction.sh`__


&nbsp;

## :information_source: Files:

* app.py: This contains the python code that runs the Flask app.
* Makefile: This contains code with commands for setup, installation and lint of project. 
* Dockerfile: This file sets up Docker image.
* run_docker.sh: Shell script responsible for creating a docker image from the Dockerfile, listing the images and starting a docker container
* upload_docker.sh: This script uploads a docker image to docker hub of ID provided.
* run_kubernetes.sh: Shell script responsible for running image in Kubernetes cluster.
* make_prediction.sh: Shell script responsible for testing deployed microservice with dummy data in order to make predictions.

&nbsp;





