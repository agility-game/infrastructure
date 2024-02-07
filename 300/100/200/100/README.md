# 100 - Workflows

If not already created, create the following file inside of the root directory of your GitHub organization ```agility-game```:

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
