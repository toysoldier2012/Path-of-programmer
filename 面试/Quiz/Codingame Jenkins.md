
# QCM

### [Jenkins] General knowledge
Jenkins (40 pts)

Which of the following statements are **correct** about **Jenkins** ?  

_Multiple answers expected._

- It is recommended to use it in a distributed Master+Agents architecture
- Jenkins projects can be triggered by Webhooks
- By default Jenkins has a Build Agent and Master Agent
- The first time Jenkins starts it will ask for the number of Executors and the default login
- The "admin" user comes by default in Jenkins

### [Jenkins] Default Environment Variables
Jenkins (20 pts)

Which of the following **Environment variables** is **not** **defined** **by default** in a build?

- NODE_URL
- NODE_NAME
- BUILD_ID
- BUILD_URL
- JENKINS_URL
- JENKINS_HOME

### [Nexus] Maven Version Policies
Nexus (20 pts)

Which of the following are **valid version policies** a **maven** **repository** **manager** can accept?

_Multiple answers expected._

- release
- snapshot
- production
- staging
- rolling
- candidate

### [Jenkins] Config endpoint
Jenkins (40 pts)

Let's suppose you have a Jenkins project named `example` at the root location. Which of the following **endpoints** will retrieve the **project definition**?

- http://JENKINS_URL/job/example/config.xml
- http://JENKINS_URL/job/example/config.json
- http://JENKINS_URL/job/example/config.yaml
- http://JENKINS_URL/job/example/job.xml
- http://JENKINS_URL/job/example/job.json
- http://JENKINS_URL/job/example/job.yaml

### [Jenkins] Project URL
Jenkins (40 pts)

Let's suppose you have Jenkins running in your **local machine** on port `8080`. In the root there is a folder named `admin` and inside this folder you have a project named `deploy-prod`.

What is the **URL** for this project?

- http://localhost:8080/job/admin/job/deploy-prod/
- http://localhost:8080/job/admin/deploy-prod/
- http://localhost:8080/job/folder/admin/job/deploy-prod/
- http://localhost:8080/job/admin/deploy-prod/job

### [Jenkins] Views
Jenkins (20 pts)

What is a **View** in **Jenkins**?

- A way to categorize and group Jenkins projects
- The main UI page that display all the projects
- A special pipeline type that allows to capture execution as video
- A configurable display for a running project
- A page that displays all the Builds of a specific project

### [Jenkins] Upstream Project
Jenkins (40 pts)

What is an **Upstream Project** in Jenkins?

- A Project that triggers different Projects during its execution
- A Project in the queue waiting for execution
- In multibranch Projects the Upstream Project is the one linked with the `master` branch
- The first Project of a multi step Pipeline

### [Jenkins] Pipeline types
Jenkins (40 pts)

What are the two types of Jenkins Pipelines?  

- Declarative and Persistent
- Persistent and Functional
- Scripted and Declarative
- Scripted and JavaScript

### [Jenkins] CI / CD
Jenkins (20 pts)

Jenkins is one of the most popular Open Source framework for **Continous Integration (CI)** and **Continous Delivery (CD)**.

Select the **definitions** that **best describe** these terms.

- **CI**: software engineering practice where team members automatically build and integrate their work
- **CD**: an extension of CI that packages and releases the artifacts built and tested by the CI
- **CI**: software engineering practice where integrated external APIs are continuously checked for downtime
- **CD**: software engineering practice that ensure that all code is properly stored in an SCM (such as Git)

### [Jenkins] Executors project queue
Jenkins (20 pts)

What happen when the **maximum** amount of **executors** is reached in a **Jenkins Agent**?

- The build will be place in queue waiting for the next available executor
- The build will be lost
- The Project will be executed in a empty workspace
- Jenkins will thrown an Error warning you have reached the maximum number of executors

### [Jenkins] Workspaces
Jenkins (20 pts)

What is a **workspace** in a **Jenkins** **Project**?

- The folder in which the project will run
- A string identifier that allows to conceptually group projects together
- The amout of memory allocated to a Project
- A folder containing multiple projects and configuration

### [Jenkins] Jenkins Plugins Programming Language
Jenkins (20 pts)

In which **programming** **language** are Jenkins **plugins** written ?

- Java
- Groovy
- Javascript
- Python
- Go
- C

### [Nexus] Maven coordinates
Nexus (20 pts)

Maven artifacts are referenced by **coordinates**.

Which of the following is **not a valid** coordinate?  

- groupName
- version
- groupId
- artifactId

# Text

# Code
