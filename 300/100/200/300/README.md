# 300 - Workflows

If not already created, create the following file inside of the root directory of your GitHub organization ```agility-game``` repository ```agility-game/home```:

```
# .gitlab-ci.yml
default:
  image: node:19

stages:
  - test

test:
  stage: test
  script:
    - echo "Hello world"
```

github.com/agility-game/home/.gitlab-ci.yaml

Let's look at some of the configuration options included in this workflow. 

We start by defining *how* GitLab should execute our jobs with its CI runner(s). We do this by setting the **image** option under the **default** section. All options we define under the **default** section automatically apply to all jobs (unless we override the options for individual jobs). In this case we tell GitLab to run our jobs inside a Docker container and use the official **node** (JavaScript runtime) Docker container. Running your tests with Docker is useful so you can use one of the many available standard Docker images.

Next we define the available **stages** in our workflow. By default GitLab defines the **build**, **test** and **deploy** stages. GitLab uses stages to decide the order of execution of your jobs. We only really use a single job that runs tests here, so we only define the **test** stage.

The last section of our file defines our single pipeline job, also called **test** (any top-level section other than a few reserved names define your workflow jobs). The only thing our job does is to print the string *Hello world* when executed.

So once you add and commit this file to your GitHub repository (here: ```github.com/agility-game/home```) and commit, GitLab will automatically start a new CI workflow run and execute our test job eventually:

Force a commit by updating the ```README.md``` file at ```https://github.com/agility-game/home```, then push to ```main``` branch:

```
$ git add README.md
$ git commit -m 'Update README.md`
$ git push
```

![agility-game-home-build-job-6116145344](https://github.com/agility-game/infrastructure/assets/1499433/f8adac09-7454-488c-9a08-b5a702d63073)

https://gitlab.com/agility-game/home/-/jobs

And the log:

![agility-game-home-build-job-6116145344-log](https://github.com/agility-game/infrastructure/assets/1499433/9aa51950-9de1-462e-8327-2a5c3d9f25e1)

https://gitlab.com/agility-game/home/-/jobs/6116145344
