# 400 - Local Development Environment

Your CI/CD workflow will run inside a Docker container on GitLab's servers (or on your own servers if your team uses a private GitLab instance). But it's still useful to run code locally, e.g. to see if your tests pass during development or to use the ```npm``` package manager to install new packages.

You could do all this directly on your machine, but it's often useful to run code inside a Docker container as well instead. First, it makes it very easy to run any commands and code in the exact same environment: simply use the same Docker container as you use for your CI pipeline. No need to install any prerequisites or dependencies! And second, it makes things more secure as everything runs inside the container without access to your full machine.

We will simply create a new Docker Compose configuration file in our project directory and tell Docker Compose to use the same ```node``` Docker container that we already use for our GitLab CI workflow:

```
# dev/docker-compose.yml
version: '3'
services:
  node:
    image: node:19
    volumes:
      - ./../:/project
    working_dir: /project
```

github.com/agility-game/home/dev/docker-compose.yml

We can then easily start our Docker container and run code inside it by using the ```docker compose``` command to launch a shell. We can then run any commands and start our tests inside the container without affecting our main machine:

```
$ cd dev
$ docker compose run node bash
Creating dev_node_run ... done
root@d433d79213d7:/project$ # in the container
```
