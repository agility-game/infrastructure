# 600 - Running the Tests from GitLab CI/CD

We can now also tell GitLab to execute our automated tests as part of the CI pipeline. To do this, we just update our ```.gitlab-ci.yml``` file and add the following commands to the ```script``` section:

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
    - npm ci
    - npm run mocha
```

github.com/agility-game/home/.gitlab-ci.yml

This is all we need to do to set up and run our automated test suite with GitLab. Let's review this step by step:

- Script start: even before our first command executes, GitLab already retrieves all our code and makes it available inside the container. So when our first command runs in the next step, all our files (including ```package.json``` and ```test.js```) are already available.
- ```npm ci```: This command uses the ```npm``` package manager to install all required package dependencies for our project inside the container (```ci``` means clean install here). Another way to put it: we previously installed the ```mocha``` and ```chai``` packages in our development container. When GitLab runs our CI pipeline, it always starts with an empty container (except our repository files). So we tell ```npm``` to look at our ```package.json``` file here and install everything we need to run our tests.
- ```npm run mocha```: Finally we tell GitLab to run our tests. Depending on whether our tests pass or fail, GitLab would continue running additional steps or stop executing further steps if we had any.

So when you commit your new workflow file (to GitHub), GitLab will automatically start a new run for our workflow (after mirroring from GitHub). It will get the repository code, install our package dependencies and finally run our tests. The output will look something like this (depending on whether the run passes or fails):


== WE ARE HERE ==
