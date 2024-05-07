# 100 - GitHub for Source Code Management

GitLab automatically enables CI/CD pipelines for new projects. It's just a matter of adding a new configuration file called ```.gitlab-ci.yml``` to your GitHub code repository (https://github.com/agility-game/home) with instructions for GitLab on what to run. 

So simply create the following basic workflow in the root directory of your ```agility-game/home``` repository and commit it:

```
# .gitlab-ci.yml
default:
  image: node:20

stages:
  - test

test:
  stage: test
  script:
    - echo "Hello world"
    - npm ci --cache .npm --prefer-offline
    - npm run mocha

  cache:
    - key:
        files:
          - package-lock.json
      paths:
        - .npm/
```
.gitlab-ci.yml

=== WE ARE HERE =====
