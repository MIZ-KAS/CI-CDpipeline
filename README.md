
[![Python application test with Github Actions](https://github.com/MIZ-KAS/CI-CDpipeline/actions/workflows/pythonapp.yml/badge.svg)](https://github.com/MIZ-KAS/CI-CDpipeline/actions/workflows/pythonapp.yml)

# Building CI-CDpipeline


## Overview

This project demonstrate how to build Github repository from scratch and creatong a scaffolding that will assist in performing both COntinuous integration and Continuous Delivery. Some of the other actions incloud 

  * Creating Github Actions along with a Makefile, requirement.txt file
  * Application code to perform an initial lint, test and install cycle.
  * and lastly Inegrating the project with Azure Pipelines to enable Continuous Delivery to Azure App Service.

A short demo of the project is included here. 

## Status

[![Python application test with Github Actions](https://github.com/MIZ-KAS/CI-CDpipeline/actions/workflows/pythonapp.yml/badge.svg)](https://github.com/MIZ-KAS/CI-CDpipeline/actions/workflows/pythonapp.yml)

## Project Plan 

### Spreedsheet

In this [spreedsheet](https://docs.google.com/spreadsheets/d/1G2UlwSD3HVO32IbAr77t-I1oMyIP3ido7AKpit3aojg/edit?usp=sharing), I have included a quarterly and yearly plan. also included is a estimated week by week deliverables with an estimated time of difficulity for each task.


### Trello Board 

In the [trello board](https://trello.com/invite/b/pXPo2Yyz/afce1f39f9ca2cc8c565ca5800a6fad4/project-2-building-a-ci-cd-pipeline) i have included a simple board based flow as below
 * To Do,
 * In Progress and 
 * Done

 ## Create the Cloud-Based Development Environment
 
 I created a [GitHub](https://github.com/MIZ-KAS/CI-CDpipeline) Repo then created a ssh-keys in my Azure Cloud Shell environment after which i clone the newly created repo into Azure Cloud Shell, screenshoot below
 
![Git clone](Screenshoots/git-clone.PNG "Project Cloned into Azure Cloud shell")


  ## Creating the Makefile 
  
  ```bashinstall:
	pip install --upgrade pip &&\
		pip install -r requirements.txt
	
test:
	python -m pytest -vv test_hello.py

lint:
		pylint --disable=R,C hello.py

all: install lint test
```
 
 ## Creating the requirements.txt
 
   ```bashinstall:
pylint
pytest
Flask==2.0.3
pandas==0.24.2
scikit-learn==0.20.3
jinja2==3.0
```

 ## Creating the Python Virtual Environment and source into it
 
   ```bashinstall:
python3 -m venv ~/.CI-CDpipeline
source ~/.CI-CDpipeline/bin/activate
```

## Local test 

```bash
(.CI-CDpipeline) lawal@Azure:~/CI-CDpipeline$ make all
```

![Passed make all screenshoot](Screenshoots/passed-makeall.PNG "Passed make all screenshoot")

Testing it locally to check the prediction by running python app.py and running ./make_prediction.sh to see the prediction locally 

![Running python app.py screenshoot](Screenshoots/python-app-py.PNG "Running python app.py screenshoott")

![Local prediction screenshoot](Screenshoots/local-prediction.PNG "Local prediction screenshoot")



