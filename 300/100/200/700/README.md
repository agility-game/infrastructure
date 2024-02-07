# 700 - Faster CI Execution with Caching

The previously created CI workflow works great and is a robust way to run our tests. But we can speed it up a little bit by making the installation of our dependencies faster. With the previous code, ```npm``` would always try to find and download all required packages from the web. GitLab makes it easy to cache such dependencies, so we can directly restore any previous files if our dependencies didn't change between pipeline runs. Especially for larger projects with hundreds of (indirect) dependencies this can make a huge difference.

To use a package cache, we change ```npm```'s default setting and use a local ```.npm``` directory to store packages. We then tell GitLab to store any files found in this directory at the end of the pipeline run. GitLab then also automatically restores the content at the beginning of future pipeline runs. And if the content of our ```package-lock.json``` file changes (e.g. when we install new packages or update versions), GitLab would create a new hash and start a new cache for the updated versions.

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
    - npm ci --cache .npm --prefer-offline
    - npm run mocha

  cache:
    - key:
        files:
          - package-lock.json
      paths:
        - .npm/
```

github.com/agility-game/home/.gitlab-ci.yml
