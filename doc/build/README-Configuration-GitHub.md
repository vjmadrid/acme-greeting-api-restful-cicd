# Configuration GitHub

**Distributed code repository"** to work with **Git**

https://github.com/

Step to follow:

* Check Prerequisites
* Create Repository
* Prepare Repository
* Add Project
* Configure Repository





## Check Prerequisites

* Require sign in or sign -> Create GitHub user





## Create Repository

1. Create the GitHub repository REPOSITORY_NAME

For example : **acme-greeting-api-restful-cicd**

2. Verify that the repository is created

3. Create a directory path and name for the workspace WORKSPACE_NAME

PROJECT_PATH = WORKSPACE_PATH + REPOSITORY_NAME

4. Locate the WORKSPACE_PATH and clone the repository into a working directory PROJECT_PATH 

For example : /workspace-ci-cd-lab/acme-greeting-api-restful-cicd





## Prepare Repository


1. Add .gitignore File to PROJECT_PATH (manually or from GitHub)

Note : this is a proposal

``` bash
### Java ###

# Compiled class file
*.class

# Log file
*.log

# Package files
*.jar
*.war
*.nar
*.ear
*.zip
*.tar.gz
*.rar

### Eclipse ###
.metadata
.settings/
.project
.classpath
.loadpath
.recommenders

target/
bin/
tmp/

*.tmp
*.bak
*.swp
*~.nib
local.properties
```

2. Add README.md to PROJECT_PATH (manually or from GitHub)
Note : at the moment we can leave it empty

3. Add RESEARCHES.md to PROJECT_PATH (manually or from GitHub)
Note : at the moment we can leave it empty





## Add Project

1. Copy the src directory provided for the exercise on PROJECT_PATH

2. Copy the pom.xml file provided for the exercise on PROJECT_PATH

3. Verify construction

```bash
mvn clean install -Pdev
```

4. Commit and push

5. Verify Commit in the repository


### PROJECT_PATH Structure

/acme-greeting-api-restful-cicd
        |
        / /src/
        |
        / pom.xml
        |
        / .gitignore
        |
        / .README.md
        |              
        / .RESEARCHES.md





## Configure Repository

1. Create the develop branch from the master

2. Configure develop branch as default






## Authors

* **Víctor Madrid**
