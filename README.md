
# Rails API Only + Postgresql + Delayed Job + Docker

This Application is created using

- Ruby 3.2.0
- Rails 7.2
- Postgresql 17




### Installation and Running

For the installation process, first you need to install Ruby and Postgresql first, you can follow the instruction [here](https://docs.docker.com/compose/install/) to install docker and follow the next steps bellow.

- Enter the app directory, and type ```cp .env.example .env``` and it will created environtment file that look like this, and fill the variable with yours


```bash
##Docker Thing
export DOCKER_BUILDKIT=1
export COMPOSE_PROJECT_NAME=atask
export COMPOSE_PROFILES=postgres,web,worker
export SECRET_KEY_BASE=insecure_key_for_dev
export RAILS_ENV=development
export NODE_ENV=development
export WEB_CONCURRENCY=1
export RAILS_MAX_THREADS=1
export POSTGRES_USER=hello
export POSTGRES_PASSWORD=password
export DOCKER_RESTART_POLICY=no
export DOCKER_WEB_HEALTHCHECK_TEST=/bin/true
export DOCKER_WEB_PORT_FORWARD=3000
export DOCKER_CABLE_PORT_FORWARD=28080
export DOCKER_WEB_VOLUME=.:/app
# export DOCKER_POSTGRES_CPUS=0
# export DOCKER_POSTGRES_MEMORY=0
# export DOCKER_REDIS_CPUS=0
# export DOCKER_REDIS_MEMORY=0
# export DOCKER_WEB_CPUS=0
# export DOCKER_WEB_MEMORY=0
# export DOCKER_WORKER_CPUS=0
# export DOCKER_WORKER_MEMORY=0
# export DOCKER_CABLE_CPUS=0
# export DOCKER_CABLE_MEMORY=0

```
- Open Project Directory from terminal, and type ```docker compose up --build```
- In another terminal type ```./run rails db:prepare``` to setup postgresql database
- To see the API documentation you can go to the ```{yourAppURL}/api-docs```

### Note:
- Every command in terminal to access docker container must be specify with ```./run {your command}```
- Type ```./run``` to see available command