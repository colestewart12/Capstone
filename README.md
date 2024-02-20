# Capstone - link to repo(https://github.com/StuartGavidia/businessapp)
# ProConnect
## Business management app
A centralized application for companies and teams where business owners can access information on their employees including access information, pay stubs and different management features. We chose this project because it is widely applicable to the business world today that can plugin to many different types of companies. This project is important because it allows business owners to save time on different company management tasks. 

## Pre-Reqs
* Docker Desktop installed and running
* Node.js installed
* Git installed

## How to run the application
1. Clone the repo locally
Run ```https://github.com/StuartGavidia/businessapp.git``` in terminal inside directory of your choice.
2. Install node modules for React development - cd into the client folder. Then run ```npm install```
3. Build all of the Docker images and run the containers
At the root of the project run ```docker-compose build```.(Try again if it fails first time) After the build is complete run ```docker-compose up``` to run the containers. The API gateway routes all request to port 8080, accessing the services through the browser is outline below.

## How to access each service (For development)
* Frontend: https://localhost:8080
* User Service: htpps://localhost:8080/users

## Installing additional dependencies in React App (For development)
* Cd into frontend
* Run ```npm install {dependency}```
* Re-build and spin up docker containers again

* (Bug fix) If dependency is not being tracked do below: 
* While the container is running, access the container terminal session in Docker Desktop and run ```npm install```
* Spin up the docker containers again

## Installing additional dependencies in Flask App (For development)
* Cd into the corresponding service (ex: UserService). Create a virtual environment if you haven't already using ```python3 -m venv .venv```
* Source into the venv with ```source .venv/bin/activate```
* Make sure to install all the packages listed in requirements.txt by running ```pip install -r requirements.txt```(Only need to be done once on creation of venv)
* Run ```pip install {dependency}```
* Run ```pip freeze > requirements.txt``` to move into requiremnts folder
* Re-build and spin up docker containers again

## Installing Cypress to test client application
* In project directory run `npx cypress open`
* Cypress app should now be open
* Click on `E2E Testing`
* Click on preferred testing browser(Google Chrome for now)
* Click `Start E2E Testing in Chrome`
* Google Chrome should open up
* Brings you to page with specs
* Click on desired specs to run tests

## Running services you are working on (For development)
* You can build your services and their databases by themselves by ```docker-compose -f docker-compose.{developmentFeatureName}.yml build```
* You can run your services and their databases by themselves by ```docker-compose -f docker-compose.{developmentFeatureName}.yml up```
* You can stop your services and their databases by themselves by ```docker-compose -f docker-compose.{developmentFeatureName}.yml down```
* You can also build the client (with required containers) along with the specific services you are working on by running ```docker-compose -f docker-compose.yml -f docker-compose.{developmentFeatureName}.yml build```
* You can also run the client (with required containers) along with the specific services you are working on by running ```docker-compose -f docker-compose.yml -f docker-compose.{developmentFeatureName}.yml up```
* You can also stop the client (with required containers) along with the specific services you are working on by running ```docker-compose -f docker-compose.yml -f docker-compose.{developmentFeatureName}.yml down```

## Check linting for Client, CommunicationService(for development):
* Cd into respective directory(client or CommunicationService)
* Run ```npm run lint```

## Check linting for AnalyticsService, UserService(for development):
* Cd into respective directory(AnalyticsService or UserService)
* Run ```pylint $(git ls-files '*.py')```
