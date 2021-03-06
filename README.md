# Pintail Docker Example

This project is a very simple example built for a docker tutorial using Node, Express, and Angular 2.  For more information about Docker and how to get started please take a look at the tutorials accompanying this project.

[Docker Series — What is Docker?](https://medium.com/pintail-labs/docker-series-what-is-docker-9eddca88f434)

[Docker Series — Starting your first container](https://medium.com/pintail-labs/docker-series-starting-your-first-container-92dfd1dc859)

[Docker Series — Creating your first Dockerfile](https://medium.com/pintail-labs/docker-series-creating-your-first-dockerfile-573bfea4991)

[Docker Series — Cheat Sheet](https://medium.com/pintail-labs/docker-series-cheat-sheet-e1841961c61)


## Requirements

 To build you will need the [Angular CLI](https://cli.angular.io/) installed

 To run you will need [Node.js](https://nodejs.org/en/) installed

 To work with Docker you will need [Docker](https://docs.docker.com/engine/installation/) installed

 This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 1.5.0.

## Getting Started

To Build

`ng build`

To start the node server

`node server.js $HOSTNAME`

## Docker

To pull the Docker image from the [Pintail.ai Dockerhub](https://hub.docker.com/r/pintailai/pintail-whoami/)

`docker pull pintailai/pintail-whoami:0.0.1`

To run the Offical Version

`docker run -d --rm -p 80:80 --name pintail-whoami pintailai/pintail-whoami:0.0.1`

To build the image

`docker build -t pintail-whoami .`

To run your local build

`docker run -d --rm -p 80:80 --name pintail-whoami pintail-whoami`

## Docker Compose

The docker-compose.yml file is designed to explain what Docker compose is and how it works.  It simply spins up two containers by default the pintail whoami image and [jwilder/nginx-proxy](https://github.com/jwilder/nginx-proxy).  The nginx proxy is designed to automatically route and load balence to docker images running on a network.

To start up the images using Docker compose 
`docker-compose up -d`

To see the images running
`docker-compose ps`

To see the logs of all the containers Docker compose started
`docker-compose logs -f`

Once you can see that the images started up correctly go to [localhost](localhost) on you machine to see pintail-whoami running

To scale up the number of pintail-whoami containers running
`docker-compose up --scale pintail-whoami=2 -d`

After you have scaled up the number of pintail-whoami containers running greater than one you can refresh [localhost](localhost) and you should the ID beneath "Welcome to the Pintail.ai Docker Example!" change.  This indicates that the nginx-proxy is forwarding you to different Docker containers!

