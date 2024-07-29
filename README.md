# time-tracker
Java (Maven) application for tracking time on the job

Time tracker

Good Night Students!!! Poll SCM Schedule,
________________________________________________________________________________________________
# ☑️CICD Pipeline Jenkins without java we can't run jenkins before installing jenkins first install java
### Version Control Github
- https://youtu.be/vxSXqvQy95g?si=GhH9MriOhJiNupRu

**Setups-Download-git,Downlaod-Java,Download-Apache-Maven,Downlaod-Jenkins**

## continus intgration mean
`continus Build + continus teat`

- CICD Mean you are writing code on your vscode and pushing on git and you can see on your sever means your web-application something has been changed
in between this things possible to happed due to jenkind

### Here's how you can describe the pipeline shown in the image:

1. **Developer (Code - Commit)**
   - The developer writes the code and commits it to a version control system (Git).

2. **Git**
   - The committed code is pushed to a remote repository hosted on Git.

3. **Jenkins**
   - Jenkins detects the new commit and triggers the CI/CD pipeline.

4. **Pipeline Stages:**
   - **Commit**
     - The pipeline is triggered by the code commit.
   
   - **Build**
     - Jenkins builds the application using tools like Maven, Gradle, or other build tools.

   - **Test**
     - The application undergoes automated testing (unit tests, integration tests, etc.).

   - **Stage**
     - The application is staged for deployment, preparing it for production. This may include further testing in a staging environment.

   - **Deploy**
     - The application is deployed to the production environment.

5. **Production**
   - The application is live and accessible to users.

### Jenkins Pipeline Script (Jenkinsfile)

```groovy
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'mvn clean install'  // Replace with your build command
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'mvn test'  // Replace with your test command
            }
        }
        stage('Stage') {
            steps {
                echo 'Staging...'
                // Add your staging steps here
                // For example, deploying to a staging environment
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Add your deploy steps here
                // For example, deploying to production
            }
        }
    }
}
```

- This script represents the pipeline shown in the image, with stages for build, test, stage, and deploy, running within Jenkins as part of a CI/CD process.

### jenkins port-number 8080
- jenkins is a framework and jenkins architecture is master-slave one master distribute task with slaves

### Pipeline of work
- ➡️ Developer ➡️ Github ➡️ Jenkins ➡️ Mavan for Build ➡️ selenium for Test ➡️ checkstyle for QA ➡️ deployment and delivery - delivery mean after building and test we give the project of client and deployment means we build test and deployment 

### Maven Building process
- ➡️ Maven ➡️ compile ➡️ code-review ➡️ unit-testing ➡️ intigration-testing ➡️ Packaging - war, jar

## Jinkins installation Getting Started by Defult first time install plugin list
Sure, here is a list of Jenkins plugins that you mentioned, which can be installed by default to extend its functionality:

### Jenkins Default Plugins

1. **Folders** - Organize jobs into hierarchical folders.
2. **OWASP Markup Formatter** - Provides security markup formatter for Jenkins.
3. **Build Timeout** - Configures build timeouts.
4. **Credentials Binding** - Allows credentials to be bound to environment variables.
5. **Timestamper** - Adds timestamps to the Console Output.
6. **Workspace Cleanup** - Cleans up the workspace before or after a build.
7. **Ant** - Integrates Apache Ant.
8. **Gradle** - Integrates Gradle.
9. **Pipeline** - Supports building continuous delivery pipelines.
10. **GitHub Branch Source** - Adds GitHub Branch as a source for multi-branch Pipeline.
11. **Pipeline: GitHub** - Integrates GitHub with Jenkins Pipeline.
12. **Groovy Libraries** - Loads Groovy libraries for Jenkins Pipeline.
13. **Pipeline Graph View** - Visualizes Jenkins Pipeline jobs.
14. **Git** - Integrates Git with Jenkins.
15. **SSH Build Agents** - Adds SSH build agents for Jenkins.
16. **Matrix Authorization Strategy** - Provides matrix-based security authorization.
17. **PAM Authentication** - Integrates PAM (Pluggable Authentication Modules) for authentication.
18. **LDAP** - Integrates LDAP for authentication.
19. **Email Extension** - Provides extended email notification functionality.
20. **Mailer** - Sends email notifications.
21. **Dark Theme** - Adds a dark theme to Jenkins for a better visual experience.

### Installing Plugins in Jenkins

To install these plugins, follow these steps:

1. **Access Jenkins Plugin Manager:**
   - Open Jenkins.
   - Go to "Manage Jenkins" > "Manage Plugins".

2. **Install Plugins:**
   - Search for each plugin name listed above.
   - Check the box next to each plugin.
   - Click on "Install without restart" or "Download now and install after restart".

### Jenkins CLI Installation Script

Alternatively, you can use the Jenkins CLI to install these plugins. Below is a script to install all the listed plugins using the Jenkins CLI:

```bash
# Download Jenkins CLI
wget http://localhost:8080/jnlpJars/jenkins-cli.jar

# Define Jenkins URL and credentials
JENKINS_URL=http://localhost:8080
JENKINS_USER=your_username
JENKINS_PASSWORD=your_password

# Install plugins
java -jar jenkins-cli.jar -s $JENKINS_URL -auth $JENKINS_USER:$JENKINS_PASSWORD install-plugin \
  cloudbees-folder \
  antisamy-markup-formatter \
  build-timeout \
  credentials-binding \
  timestamper \
  ws-cleanup \
  ant \
  gradle \
  workflow-aggregator \
  github-branch-source \
  pipeline-github \
  pipeline-groovy-lib \
  pipeline-graph-analysis \
  git \
  ssh-slaves \
  matrix-auth \
  pam-auth \
  ldap \
  email-ext \
  mailer \
  dark-theme

# Restart Jenkins to apply changes
java -jar jenkins-cli.jar -s $JENKINS_URL -auth $JENKINS_USER:$JENKINS_PASSWORD safe-restart
```

Replace `your_username` and `your_password` with your Jenkins credentials. Run this script in your terminal to install the plugins and restart Jenkins.

- This list ensures you have a robust Jenkins setup with essential plugins for various functionalities, enhancing your CI/CD pipeline.
______________________________________________________________________________________________________________________________________

## Jenkins Practice
- Jenkins Plugin Install
   - Maven intigration
   - Green Balls
    
- Jenkins Global Tool Configuration - we can set like environment variables path in jenkins inside Global Tool Configuration

- Pull project form github - PS C:\> git clone https://github.com/HackBugs/time-tracker.git
- cd C:\> cd .\time-tracker\
- CMD Of Maven - mvn clean package
______________________________________________________________________________________________________________________________________

### Set Jenkins Environment Variables
- http://localhost:8080/configureTools/

### Manage Jenkins
  - Plugins
  - Credentials
      - Create Credential to use groovy code without showing password
  - Users
      - User1
      - user2
      - user3
  - Manage and Assign Roles
      - Install plugin > Role-based Authorization Strategy
      - First check if your role mangement is working than not need to install this plusgin if not working than - Install plugin Authorize ProjectVersion
    
    - Security > Authorization > Role-Based Strategy
    
    - Manage and Assign Roles
      - Manage Roles
      - Assign Roles
      - Permission Templates
      - Role Strategy Macros

### Project Configure Section
 - Build periodically
 - GitHub hook trigger for GITScm polling
 - Poll SCM
  
### Source Code Management
  - Git

### Post-build Actions
  - Build Other Project

### Jenkins-CICD-django-notes-app - Configuration
- Pipeline
    - Pipeline script - in this we write groovy code
    - Pipeline script from SCM - in this groovy upload on github and set the path
______________________________________________________________________________________________

### Master Slave Concept - Job Distribution concept
   - Dashboard > Manage Jenkins > Nodes > New node
   - Remote root directory > c:\slave1
   - Launch method > section option > download jarfile and set the path of jar agent/slave1 path
   - Go all node section and select the slave > configure > label > preference
   - Now if you want multiple project then go inside project > configure > Restrict where this project can be run
______________________________________________________________________________________________________________________

### Install on linux Ubuntu
```sh
apt-get update
sudo apt-cache search openjdk
sudo apt-get install openjdk-21-jdk
Java --version
Follow the download documentation of jenkins based on operating system
```
____________________________________________________________________________________________________________________

### Maven
   - Pom.xml - Configuration file -
      - Metadata
      - Source
      - Dependencies Information
      - Compiler Information
      - .War .Jar
      - Kind of Project
      - Kind of output
   - in one Pom.xml contain on project infomation not multipule
     
### Architecture of Maven
   - M2 Local Repo - first maven try to donload Dependencies from local repo if local repo have not Dependencies than it's reach to Centeral repo > Pom.xml - we mention all Dependencies and Compiler and other information | Goal - all cmd of maven we called gols > Source code > Remotec Centeral Repo where maven Dependencies or other requrement have stored > Github where we save our code
   - From MVN community you can download Dependencies also if you need of any other Dependencies
________________________________________________________________________________________________________________________

### Ant and Maven
### Ant 
   - Toolbox
   - Does Haven't formal conversation - not set define things
   - Ant is procedural
   - Not have lifecycle
### Maven
   - Framework
   - You can configuartion can desigin you folder and other things
   - Project Management tool
   - Have formal conversation - Have rule to create folder structure and your write code there only
      - where you download source code
      - Compiled code 
      - Define in Pom.xml
   - Maven is declarative - maven know becouse what have work bec everything is we define Pom.xml file
   - Follow lifecycle

### Maven Folder Structure
Maven follows a standard directory structure for its projects. This structure helps in organizing the project files in a consistent manner, making it easier for developers to understand and manage the project. Below is the typical structure of a Maven project:

```
my-app/
├── pom.xml
└── src
    ├── main
    │   ├── java
    │   │   └── com
    │   │       └── mycompany
    │   │           └── app
    │   │               └── App.java
    │   ├── resources
    │   │   └── application.properties
    │   └── webapp
    │       ├── WEB-INF
    │       └── jsp
    └── test
        ├── java
        │   └── com
        │       └── mycompany
        │           └── app
        │               └── AppTest.java
        └── resources
```

### Explanation of the Directory Structure:

1. **my-app/**: Root directory of the project.
2. **pom.xml**: The Project Object Model file that contains information about the project and configuration details used by Maven to build the project.

3. **src/**: Source folder containing all the project source files.
    - **main/**: Main source directory.
        - **java/**: Java source files.
            - **com/mycompany/app/**: Package structure for the Java classes.
                - **App.java**: Main application class.
        - **resources/**: Resource files like configuration files (e.g., application.properties).
        - **webapp/**: Web application directory (for web projects).
            - **WEB-INF/**: Contains web application specific files like web.xml.
            - **jsp/**: Directory for JSP files.
        
    - **test/**: Test source directory.
        - **java/**: Java test files.
            - **com/mycompany/app/**: Package structure for the test classes.
                - **AppTest.java**: Test class.
        - **resources/**: Resource files for tests.

### Customizing the Directory Structure:

Maven allows you to customize the directory structure by configuring the `pom.xml` file. For example, you can specify different directories for source and resource files.

This standard directory structure helps in streamlining the build process and makes it easier for developers to understand and collaborate on Maven projects.
______________________________________________________________________________________________________________________________________________________________________________

### Maven Project with Apache Tomcat janken.war
 - Downlaod
      - Git
      - Oracle jave JDK
      - Jenkins.war - For running inside topcat server
      - Apache Tomcat Server - Test tomcat is runing `localhost:8080`
      - Create folder `C:\JENKINSHOME` - Set environment variables as like you set of Java
      - Restart you PC
      - Paste the Jenkins.war file on this location - C:\Program Files\Apache Software Foundation\Tomcat\[version]\webapps
      - Open open jenkins - `localhost:8080/jenkins`
      - Install jenkins plugin - `gibhubpull`, `Build check code is running or have error`, `install Junit plugin`
      - Deploy - install jinkins plugin - `deploytocontainer`
      - clone the github project - in jenkins
   

