# Configuration Travis CI

**Code Coverage repository"** to work with **Git**

https://codecov.io/

Step to follow:

* Check Prerequisites
* Create/Configure Workspace
* Import Project





## Check Prerequisites

* Sign up with GitHub
* Accept the Authorization
* Select the repositories you want to use

https://codecov.io/gh/GITHUB_USERNAME/GITHUB_REPOSITORY.

https://codecov.io/gh/vjmadrid/acme-greeting-api-restful-cicd

* Copia el TOKEN

96972cef-a2c4-4694-b63a-11910a3b34ec
96972cef-a2c4-4694-b63a-11910a3b34ec

Use this token when uploading reports to this repository.
You can set it in your CI environment variables. CODECOV_TOKEN="96972cef-a2c4-4694-b63a-11910a3b34ec"

* Vale 

https://docs.codecov.io/docs/supported-languages

https://github.com/codecov/example-java
  * JACOCO

https://github.com/codecov/example-java-maven
  * Cobertura maven plugins




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
