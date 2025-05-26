# WebShop Application with Component

This backend provides a small web-application consisting of a [pedestal](http://pedestal.io/)
service, and a database connection to persist items. These two components are compose in 
a system with Stuart Sierra's [Component](https://github.com/stuartsierra/component) 
library. The repo is based on [n2o's ToDo app](https://github.com/n2o/component-todo-app).

## Requirements

Short and crisp: Always have [Docker](https://docs.docker.com/install/) installed.

Do you want to run the app virtualized with docker?
* Yes: Then you will need [Docker Compose](https://docs.docker.com/compose/install/).
* No: Please have [Leiningen](https://leiningen.org/#install) installed as build tool.

## Setup

The app needs a postgres database. You can create a database with correct
settings via (pls skip this step if you got docker):

    docker run --rm \
        -e POSTGRES_PASSWORD=clojure \
        -e POSTGRES_USER=clojure \
        -e POSTGRES_DB=clojure \
        -p 5432:5432 \
        postgres:12-alpine

Then you can start the system:

    lein run


The service is reachable via http://localhost:8080, and the swagger file is on http://localhost:8080/swagger.

### No Clojure/Leiningen installed?

No problem, please use:

    docker-compose up

### Tests

There are sample tests, which can be run with

    lein test

### Helper

You can run multiple helping tools like code formatting, linting, interactive 
dependency checker and code analyzer via:

    lein cljfmt fix
    lein eastwood
    lein ancient upgrade :interactive
    lein kibit
