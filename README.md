# Jenkins

This git repository contains necesary services for used Jenkins
with docker and docker-compose inside.

## Technologies stack

- [Docker](https://docs.docker.com/engine/install/)
- [Docker Compose](https://docs.docker.com/compose/install/)
- [Jenkins](https://www.jenkins.io/)

## Get started

1. Install Docker and Docker Compose

2. Change sockets permission for jenkins access to docker

		$ sudo chmod 666 /var/run/docker.sock

3. Set environment variables

		$ source envs

4. Run Jenkins service and detach

		$ export COMPOSE_FILE=production.yml

		$ docker-compose up -d

4. Check port 8080 is open and go to http://your-domain:8080

5. Get password and start Jenkins

		$ docker-compose logs

## Networks

If you need to connect to an external network that belong to other
services, run Jenkins with:

	$ export COMPOSE_FILE=proxy_network.yml

	$ docker-compose up -d

Rename the external network with your external network name.

Example:

	networks:
	proxy:
	  external:
	    name: <your-external-network-name>
