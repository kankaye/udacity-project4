[![CircleCI](https://dl.circleci.com/status-badge/img/gh/kankaye/udacity-project4/tree/main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/kankaye/udacity-project4/tree/main)

## Project Overview

In this project, we will deploy machine learning Microservice API which predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on

---

## Instructions

* Create a virtualenv with Python 3.7 and activate it. 
```bash
python3 -m pip install --user virtualenv
python3 -m venv ~/.devops
source ~/.devops/bin/activate
```
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

## Explanation of the files in the repository

1. `Dockerfile` includes the instructions of how to containerize the application `app.py`. 
2. `make_predictions.sh` is to make house price predictions, we need to run the shell script  while the app is up. In this script, it send a POST request to containerized application via the appropriate portwith a json object that contains the concrete values (the input) of the features of the prediction model.
3. `docker_out.txt` and `kubernetes_out.txt` give examples of the expected output of running the app in Docker and Kubernetes. 
4. `upload_docker.sh` file is used to share the created Docker image
5. `config.yml` in `.circleci` folder is to setup a CICD pipeline to fully automate the process
