# Configuration Travis CI

**Distributed code repository"** to work with **Git**

https://travis-ci.com

https://docs.travis-ci.com/user/tutorial/

Step to follow:

* Check Prerequisites
* Create/Configure Workspace
* Import Project





## Check Prerequisites

* Sign up with GitHub
* Accept the Authorization
* Select the repositories you want to use





## Configure Project

Add a .travis.yml file

```bash
language: java

jdk:
- openjdk8

branches:
  only:
  - develop
```

Add the .travis.yml file to GitHub -> Commit and push





## Build Project with Travis CI

* OPTIONAL : Change code

* Commit and push

* Trigger a Travis CI build (require .travis.yml file)

* Verify the build status -> visiting Travis CI and selecting your repository





### Add Information

Add the following sentence in the "README.md" file

```bash
[![Build Status](https://travis-ci.com/vjmadrid/acme-greeting-api-restful-cicd.svg?branch=develop)](https://travis-ci.com/vjmadrid/acme-greeting-api-restful-cicd)
```

## Authors

* **Víctor Madrid**
