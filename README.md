
# Simple Blog Sample Application with Django

[![CircleCI](https://circleci.com/gh/bebekhan/my-first-blog.svg?style=svg)](https://circleci.com/gh/bebekhan/my-first-blog)

This is an example application showcasing how to run a Python Django app on CircleCI 2.1. 

<!-- To see how these steps would be configured in a 2.0 config, please check out the [master branch](#UPDATE LINK). -->

<!-- To see these features in a version 2.1 config with reusable commands and running on different executors, please see the [2.1-simplified-config branch](#UPDATE_LINK). -->


## Sample configurations: version 2.1
- [A basic build with an orb](#a-basic-build-with-an-orb)


### A basic build with an orb
```yaml
version: 2.1

orbs:
  python: circleci/python@0.2.1

jobs:
  build-and-test:
    executor: python/default
    steps:
      - checkout
      - python/load-cache
      - python/install-deps
      - run:
          name: Test
          command: ./manage.py test
      - python/save-cache

workflows:
  main:
    jobs:
      - build-and-test
```
This config uses the language-specific orb to replace any executors, build tools, and commands available. 
Here we are using the [python orb](https://circleci.com/orbs/registry/orb/circleci/python), which works with the pip cache on CircleCI to speed up builds. 
The `python/load-cache` command loads cached pip packages.
The `python/install-deps` command saves pip packages to cache.
The parameters of this command can be customized. See the docs for more information.
