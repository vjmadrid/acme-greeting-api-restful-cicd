# Configuration IDE

**Integrated Development Environment** to develop software

Step to follow:

* Check Prerequisites
* Create/Configure Workspace
* Import Project





## Check Prerequisites

* Select IDE : Eclipse , Idea, ...
* Verify that the IDE to be used is installed
* Verify that it has integration with maven





## Create/Configure Workspace

1. Create a workspace on the WORKSPACE_PATH

Select the workspace

2. Verify that the ide meta-information has been created

For example (Eclipse) : 

/workspace-ci-cd-lab
        |
        / .metadata                             **META**
        |
        / acme-greeting-api-restful-cicd
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

3. Configure the installation of the JDK on which you want to work

For example (Eclipse) : Preferences > Java > Installed JREs

4. Configure the default JRE for the JDK

5. Configure the Maven installation you want to work on

For example (Eclipse) : Preferences > Maven > Installations

6. Configure Text File Encoding : UTF-8

Configure the encoding on which you want to work

For example (Eclipse) : Preferences > General > Workspace





## Import Project

1. Import the project with the IDE Maven

2. Verify that the ide meta-information has been created

For example (Eclipse) : 

/workspace-ci-cd-lab
        |
        / .metadata                         **META**
        |
        / acme-greeting-api-restful-cicd
                |
                / .project                  **META**
                |
                / .classpath                **META**
                |
                / ./settings/               **META**
                |
                / src
                |
                / pom.xml
                |
                / .gitignore
                |
                / .README.md
                |              
                / .RESEARCHES.md
                |              
                / /target/



## Authors

* **Víctor Madrid**
