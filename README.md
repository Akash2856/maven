# simple-java-maven-app

This repository is for the
[Build a Java app with Maven](https://jenkins.io/doc/tutorials/build-a-java-app-with-maven/)
tutorial in the [Jenkins User Documentation](https://jenkins.io/doc/).

The repository contains a simple Java application which outputs the string
"Hello world!" and is accompanied by a couple of unit tests to check that the
main application works as expected. The results of these tests are saved to a
JUnit XML report.

# Scalable Jenkins CI/CD: Master-Slave Configuration

## Project Overview

This project focuses on the implementation of a Jenkins master-slave architecture to streamline Continuous Integration/Continuous Deployment (CI/CD) processes. It enables efficient software builds and deployments through a set of orchestrated steps.

## Installation and Configuration

### Master OS

- **Jenkins Installation**: We started by installing Jenkins on the master OS and configured it for functionality.

### Job Setup on Master OS

- **Job1 for GitHub Integration**: A job named 'Job1' was created to download code from GitHub and store it in the `/var/lib/jenkins/workspace/JOB_NAME` directory.
- **Adding a New Node**: A new node was added to Jenkins to establish connectivity with the slave OS.
- **Agent Installation on Slave**: An agent was installed on the slave OS to connect with the master and execute instructions sent from the master. During the node configuration, the agent was set up, including specifying the OS's IP, username, and SSH private key (password or private key) for secure communication.
- **Label Assignment**: Each node was given a label, specifying the location where the slave OS would store files downloaded by 'Job1' from GitHub.
- **Host Key Verification**: Host key verification was set to "non-verifying verification" for ease of communication.
- **Configuration Save**: After setting up the agent and job configuration, all settings were saved for activation.
- **Maven Plugin Installation**: The Maven plugin was installed in Jenkins to facilitate the building of projects on the slave OS.

### Job Creation for Building

- A job was created with a specified slave node label, ensuring that the job ran on the designated slave. The job was set to build Java code, using the 'clean package' goal and the 'pom.xml' path. Post-build actions included archiving the artifact, specifying the location for the .JAR file.

### Slave OS Configuration

- **Agent Installation**: The slave OS had the Jenkins agent installed, which is a Java program. This involved installing the Java Development Kit (JDK) and Maven on the slave OS.
- **Workspace Directory Setup**: Within the slave node, workspace directories were configured to specify where files should be stored. A folder named 'jenkinsws' was created in the slave OS, and Jenkins jobs automatically added new folders within 'jenkinsws' to organize workspace for different jobs under 'JOB_NAME'.

## Project Impact

This project demonstrates the ability to set up an efficient master-slave architecture in Jenkins for scalable and streamlined CI/CD processes, significantly improving the speed and reliability of software builds and deployments.

Feel free to use or modify this project for your own CI/CD requirements. If you have any questions or need further assistance, please don't hesitate to reach out.

