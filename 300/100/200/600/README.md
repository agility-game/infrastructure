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
    - npm ci
    - npm run mocha
```

github.com/agility-game/home/.gitlab-ci.yml

== WE ARE HERE ==
