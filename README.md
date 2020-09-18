[![ManuelECdev](https://circleci.com/gh/ManuelECdev/UdaProject4.svg?style=svg)](https://circleci.com/gh/ManuelECdev/UdaProject4)

## Project summary

The project's scope is to operationalize a Machine Learning Microservice API. 

The model has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. 

In this project the Machine Learning Microservice API is given and the scope is to implement a Dockerfile, Makefile, run_docker.sh, run_kubernetes.sh, upload_docker.sh and .circleci/config.yml

## Files 

* Dockerfile:

This file is used for building a docker container.

* Makefile: 

This file is used for automatize the execution of some functions like installing dependencies, running circleci locally, lint etc...

* run_docker.sh

This is script is for running the application as a docker container locally.

* upload_docker.sh 

This script is for uploading the docker container to docker hub.

* run_kubernetes.sh

This script is for depploying the app in a kubernetes cluster locally.

* requirements.txt

This file is for defining the required dependecies.

* .circleci/config.yml

This is file is used to give continuous integration capabilities to the app.

* make_prediction.sh

This is sript to make a request to the model to get a prediction.


## Run the app locally as standalone.

- Software requirements:
    Python3
    curl

 1. Create a virtualenv and activate it:
    python3 -m venv ~/.devops
    source ~/.devops/bin/activate
2. Install the necessary dependencies:
    make install
3. Run the app.
    python3 app.py

4. Make a prediction:
    ./make_prediction ( change port form PORT=8000 to PORT=80 )

### Running the app as docker container locally

- Software requirements:
    Docker
    curl

1. Run in Docker:  
    ./run_docker.sh
2. Make a prediction:
    ./make_prediction ( keep original PORT=8000 )

### deploying and running the app to a  kubernetes cluster locally

 - Software requirements:
    Docker
    Minikube
    Kubernetes
    curl
    Docker Hub account

 -  Other requirements:
    The container have to be build previusly with:
        docker build --tag=udaproject4 .


1. Upload the container to docker hub:
    ./upload_docker.sh
2. Deploy and run the app with kubernetes
    ./run_kubernetes.sh
3. Make a prediction:
    ./make_prediction ( keep original PORT=8000 )
