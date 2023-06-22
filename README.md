[![CircleCI](https://circleci.com/gh/JeamBeamCim/udacity-boston.svg?style=svg)](https://circleci.com/gh/JeamBeamCim/udacity-boston)
# Operationalize-a-Machine-Learning-Microservice-API
Microservice Project [Udacity Cloud DevOps Engineer Nanodegree]

## Project Overview
Deploy a containerized Python flask application to serve out predictions (inference) about housing prices through API calls. It uses a a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features. 

### Project Procedure
* Test project code using linting
* Complete a Dockerfile to containerize this application
* Deploy containerized application using Docker and make a prediction
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate the code has been tested



---
## Getting Started
### Setup the Environment

* Create a virtualenv and activate it
```
python3 -m venv ~/.devops
source ~/.devops/bin/activate
```
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

1. Setup and Configure Docker locally
   * install docker-> [howto:]https://docs.docker.com/engine/install/
   * Run `./run_docker.sh`
   * Run `docker ps` to check if docker is running.
   * Run `./make_prediction.sh` to make prediction and copy/paste the logging info at terminal to output_txt_files/docker_out.txt
2. Setup and Configure Kubernetes locally
    * Run `curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-darwin-amd64`
    * Run `sudo install minikube-darwin-amd64 /usr/local/bin/minikube`
    * Run `minikube start`
    * Run `kubectl get pods` to see which pods are running.
    * Run `./run_kubernetes.sh`
    * Run `./make_prediction.sh` to make prediction and copy/paste the logging info at terminal to `output_txt_files/kubernetes_out.txt`
3. Create Flask app in Container
    * Run `./run_docker.sh` to build and start the Flask app container.
        
   > The script will:
   > * Build an docker image
   > * List images to verify that this app is dockerized
   > * Run a container with this specified image and map port 8000 (host) to 80 (container)

   * Run `./upload_docker.sh` to upload the container to docker hub.
   
