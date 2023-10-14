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

### Master Slave Configuration

- **Job1 for GitHub Integration**: A job download code from GitHub and store it in the `/var/lib/jenkins/workspace/JOB_NAME` directory.
- **Adding a New Node**: A new node was added to Jenkins to establish connectivity with the slave OS.

  ![image](https://github.com/Akash2856/maven/assets/49570016/c1bddbcc-b261-4ec9-b309-55985e889216)

- **Label Assignment**: Each node was given a label, specifying the location where the slave OS would store files downloaded by 'Job' from GitHub.
  
  ![image](https://github.com/Akash2856/maven/assets/49570016/d55e4c56-aa19-4855-b6e3-56a6ceea2e25)

- **Agent Installation on Slave**: An agent was installed on the slave OS to connect with the master and execute instructions sent from the master. During the node configuration, the agent was set up, including specifying the OS's IP, username, and SSH private key (password or private key) for secure communication.
- **Host Key Verification**: Host key verification was set to "non-verifying verification" for ease of communication.
  
![image](https://github.com/Akash2856/maven/assets/49570016/5246dcb2-d47f-4b9b-aaf1-fe2ee05d46c8)

- **Configuration Save**: After setting up the agent and job configuration, all settings were saved for activation.
- **Maven Plugin Installation**: The Maven plugin was installed in Jenkins to facilitate the building of projects on the slave OS.
  
![image](https://github.com/Akash2856/maven/assets/49570016/1d96784d-6378-410f-9db9-a3309217c5de)


### Job Creation for Building

- A job was created with a specified slave node label, ensuring that the job ran on the designated slave. The job was set to build Java code, using the 'clean package' goal and the 'pom.xml' path. Post-build actions included archiving the artifact, specifying the location for the .JAR file.
  
![image](https://github.com/Akash2856/maven/assets/49570016/1c4b9d32-69dc-4c71-b588-2dfeae9487e4)
![image](https://github.com/Akash2856/maven/assets/49570016/5385a608-a212-49fd-bf99-d280711eed74)
![image](https://github.com/Akash2856/maven/assets/49570016/cc5d10c4-1c26-4fd2-8162-9ba050916415)
![image](https://github.com/Akash2856/maven/assets/49570016/3d48e442-02f4-4322-869d-c4c9fb59e308)

![image](https://github.com/Akash2856/maven/assets/49570016/36e6758c-3461-4301-9be3-d45010486753)


  


### Slave OS Configuration

- **Agent Installation**: The slave OS had the Jenkins agent installed, which is a Java program. This involved installing the Java Development Kit (JDK) and Maven on the slave OS. **`Remoting.jar`** has the agent data.
- **Workspace Directory Setup**: Within the slave node, workspace directories were configured to specify where files should be stored. A folder named 'jenkinsws' was created in the slave OS, and Jenkins jobs automatically added new folders within 'jenkinsws' to organize workspace for different jobs under 'JOB_NAME'.

## Project Impact

This project demonstrates the ability to set up an efficient master-slave architecture in Jenkins for scalable and streamlined CI/CD processes, significantly improving the speed and reliability of software builds and deployments.

Feel free to use or modify this project for your own CI/CD requirements. If you have any questions or need further assistance, please don't hesitate to reach out.

