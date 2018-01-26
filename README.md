# WordPress with Docker
This project is just an example how you can run WordPress in a Docker container environment

## What do I need?
First, you will have to install the following applications:
* [Docker](https://docs.docker.com/docker-for-windows/install/) - This is a Windows installation. You can also find
documentation for other Operating Systems on their website as well.

## How to run the development environment?
After you successfully installed Docker, you might want to restart your computer, since there are some environment variables
setup for you by Docker.

You can make sure that Docker is installed by typing `docker --version` or `docker-compose --version` in your command line tool

Now we are ready to boot up the development environment. Just type `docker-compose up` in your terminal. This
will pull the necessary containers for you, and it will boot up the systems. This application is configured to create
two docker containers. One is the WordPress itself, with Apache as a server. And the other one is MySQL version 5.7.

If you don't want to see the containers log on `docker-compose up`, you can just add the flag `-d`. This will
run the docker as a daemon service, and the final command will look like this `docker-composer up -d`

In your browser navigate to [127.0.0.1:8080](http://127.0.0.1:8080) or [localhost:8080](http://localhost:8080) and you should see the application.
On the first run, you will see the setup wizard from WordPress. In future, we will have some type of database replication from QA
so this step will not be needed.

# Any useful commands?
Docker and Docker Compose have a lot of CLI commands, but here are some that you might use every day.

### Running the containers
`docker-compose up -d`

### Stopping containers
`docker-compose kill`

### Removing containers
`docker-compose rm`

### Force rebuild - after changes to the Dockerfile
`docker-compose up -d --no-deps --build`

### Run a command in some container
`docker-compose exec <service-name> <command>`

### ssh in container/service
`docker exec -it <CONTAINER_NAME> /bin/bash`