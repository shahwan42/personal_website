# arm_portfolio
Ahmed, Ramy, and Mohamed's Portfolio Website

![Django CI](https://github.com/shahwan42/arm_portfolio/workflows/Django%20CI/badge.svg?branch=develop)

## Environment Setup

Install the following:
- [docker](https://docs.docker.com/engine/install/)
- [pyenv](https://github.com/pyenv/pyenv)
then install python 3.8.2, make it global (read pyenv's documentation for details)
- [virtualenvwrapper](https://virtualenvwrapper.readthedocs.io/en/latest/)
install virtualenvwrapper inside pyenv's python and configure it according to its documentation
- `$ mkvirtualenv pp` to create a virtualenv for the project (pp=portfolio project)
- go to the project dir and `$ pip install -r requirements.txt`
- [docker-compose](https://docs.docker.com/compose/install/)
then `$ docker-compose -f local.yml up` to run the servers locally
- start coding

*We can run our code on docker without a virtual environment, however, installing the local virtual environment helps us with code completion, linting, and formatting in VS Code (or any editor) which are important factors*

## Local development

- Go to the project directory
- Activate the virtualenv `$ workon arm_portfolio`
- if you want to make sure you've got latest dependencies `$ pip install -r requirements.txt`
- run the project servers `$ docker-compose -f local.yml up`

** TODO script to shorten docker-compose commands--- continue this section after the script


## Team Workflow

In our GitHub repo we're going to have 2 main branches
- master -> Will be connected to a CD pipeline that continuously deploy the code to Heroku, then after sometime, it will be connect to a VPS of our own.
- develop -> The branch of new features to develop

I will setup a CI and connect it to the repo

When you're going to do a new task, you're going to do the following:
- update your local develop branch `$ git checkout develop && git pull origin develop`
- take another branch from develop for your task `$ git checkout -b my_task_branch`
- write code to suffice the requirements of your task
- push your code to the repo `$ git push origin my_task_branch`
- create a Pull Request from the repo's page on GitHub, the base branch must be `develop`
- your code updates must pass the CI checks (testing/code formatting) if it passes, I will review the code and write hints
- if your updates have conflicts with the base branch (develop) you must solve those conflicts yourself
- we might get into meetings to fix issues together or review code together, until we're settled that the code is ready to be merged
- I will merge the code into the `develop` branch
- when we reach a certain point on `develop` I will merge it to the `master` branch, and the features we're working on will be deployed to Heroku/our VPS

