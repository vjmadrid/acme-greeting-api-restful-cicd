# Configuration Codecov

**Code Coverage repository"** to work with **Git**

https://codecov.io/

Step to follow:

* Check Prerequisites





## Check Prerequisites

* Select repository Git Hub

```bash
https://codecov.io/gh/GITHUB_USERNAME/GITHUB_REPOSITORY
```

* Sign up with GitHub
* Accept the Authorization
* Select the repositories you want to use
* Copy TOKEN (use a temporal file :-) )
* Select language 

https://docs.codecov.io/docs/supported-languages

https://github.com/codecov/example-java
  * JACOCO

https://github.com/codecov/example-java-maven
  * Cobertura maven plugins

* Add "CODECOV_TOKEN" Enrironment Variable in the CI

Option 1 : set it in your CI environment variables. CODECOV_TOKEN


## Configure Travis CI

1. Add environment variables : CODECOV_TOKEN

OPTION 1 : Add in Travis CI WEB Settings

OPTION 2 : Add in .travis.yml file

```bash
...
env:
  global:
    - CODECOV_TOKEN=:uuid-repo-token
```


Add a .travis.yml file

```bash
...
after_success:
  - bash <(curl -s https://codecov.io/bash)
```

Add the .travis.yml file to GitHub -> Commit and push





## Authors

* **Víctor Madrid**
