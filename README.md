# charges-app stack

This repository contains the docker-compose.yml configuration file to set up the environment to deploy the charges-server API and the charges-consumer web app.

## Requirements

- Linux distro
- Node == 10.x
- Docker > 18.x
- Docker-compose > 1.23.x

## Features

This is the application list of features:

```
Feature: List charges

  Scenario: In the main page
    Given the app is running
    When the user navigates to the main view
    Then a list of charges will be displayed
```

```
Feature: Show charge detail

  Scenario: In the main page
    Given the app is running
      And the user is in the main view
    When the user clicks on the show button of one charge element
    Then a detail view will be displayed
```

```
Feature: New charge

  Scenario: In the main page
    Given the app is running
      And the user is in the main view
    When the user clicks on the create button
    Then a charge creation view with a form will be displayed

  Scenario: In the creation view
    When the user fill up the form fields
     And the user clicks on send button
    Then a new charge will be stored in the database
     And the user will be redirected to main view
```

```
Feature: Delete charge

  Scenario: In the main page
    Given the app is running
      And the user is in the main view
    When the user clicks on delete button of one charge element
    Then the charge element will disappear from the list
```

## Installation

Clone the source code and the git submodules charges-server and charges-consumer:

`$ git clone --recursive https://github.com/esteban24/charges-app.git`

And you are ready to go, let's start up the stack with docker-compose

`$ docker-compose up`

And enjoy!

To check everything is OK:

- charges-server: `$ curl http://localhost:3001/ping`
- charges-consumer: `$ curl http://localhost:5000/ping`

