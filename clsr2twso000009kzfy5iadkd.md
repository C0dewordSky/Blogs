---
title: "Day 23 - Jenkins Freestyle Project"
seoTitle: "Jenkins Freestyle Project"
datePublished: Sun Feb 18 2024 05:38:12 GMT+0000 (Coordinated Universal Time)
cuid: clsr2twso000009kzfy5iadkd
slug: day-23-jenkins-freestyle-project
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1708234437104/bc40f4e8-0ba9-41db-affa-f4855713d9b0.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1708234672291/5017c060-2bbd-4b35-8a0f-4ea2b807e6fb.png
tags: docker, aws, devops, hashnode, jenkins, 2articles1week, technical-writing-1, devops-articles, jenkins-devops, devops-journey, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge, devopscommunity

---

## Introduction

Greetings, DevOps enthusiasts! 🚀 Today marks another thrilling milestone in our #90daysofdevops journey as we delve into the realm of Jenkins Freestyle Projects. So, buckle up and prepare to elevate your abilities to new heights!

### Summarizing CI/CD:

Before we dive into the nitty-gritty of Jenkins Freestyle Projects, let's take a moment to refresh our knowledge of CI/CD concepts.

Continuous Integration (CI) automates the integration of code modifications from multiple builders into a single codebase, facilitating faster bug detection, improving software quality, and streamlining the integration process.

Continuous Delivery (CD) ensures error-free releases by automating the deployment process, making it seamless and efficient.

### Exploring Build Jobs:

![](https://cdn.ttgtmedia.com/rms/editorial/TSS_jenkins_build_job_fig3_mobile.png align="center")

In Jenkins, build jobs are the backbone of automation. These jobs include the configuration for automating specific tasks in the software building process, ranging from compiling code to running tests and deploying applications.

Jenkins offers various types of build jobs, including freestyle projects, pipelines, multi-configuration projects, and more, to cater to diverse requirements.

The key points about build jobs in Jenkins:

1. **Purpose**: Automate tasks in the software development lifecycle.
    
2. **Configuration**: Defined using Jenkins web interface or Jenkinsfile.
    
3. **Build Steps**: Individual tasks within a build job (e.g., compiling code, running tests).
    
4. **Post-Build Actions**: Actions executed after build steps (e.g., archiving artifacts, sending notifications).
    
5. **Build History and Logs**: Records build executions and provides detailed logs.
    
6. **Build Triggers**: Events or conditions that initiate build executions (e.g., code commits, time schedules).
    
7. **Plugins and Integrations**: Extends functionality and integrates with external tools and services.
    

### Unveiling Freestyle Projects:

Now, let's unravel the concept of Jenkins Freestyle Projects—a versatile tool that empowers DevOps engineers to build, test, and deploy software with ease. Imagine you're working on an application deployed via Docker. Here's where Jenkins Freestyle Projects shine:

## Hands-On Practice

# Task-01

* create a agent for your app. ( which you deployed from docker in earlier task)
    
* Create a new Jenkins freestyle project for your app.
    
* In the "Build" section of the project, add a build step to run the "docker build" command to build the image for the container.
    
* Add a second step to run the "docker run" command to start a container using the image created in step 3.
    

# Task-02

* Create Jenkins project to run "docker-compose up -d" command to start the multiple containers defined in the compose file (Hint- use day-19 Application & Database docker-compose file)
    
* Set up a cleanup step in the Jenkins project to run "docker-compose down" command to stop and remove the containers defined in the compose file.
    

**Scenario-Based Tasks:**

**Task-01: Building and Deploying Docker Containers**

Imagine you have developed an application deployed via Docker, and your mission is to create a Jenkins Freestyle Project to automate the build and deployment process. Let's break it down:

**Solution:**

1. **Set up an agent for your app:**
    
    Begin by configuring an agent to handle the build and deployment tasks for your Dockerized application. You can specify this directly in your Jenkinsfile or in the Jenkins interface.
    
    ```bash
    agent any // Or specify a label for a specific agent
    ```
    
2. **Create a new Jenkins freestyle project:**
    
    Within Jenkins, navigate to the dashboard and create a new freestyle project tailored to your application's needs.
    
3. **Configure the "Build" phase:**
    
    In the project configuration, navigate to the "Build" section and add a build step to execute the "docker build" command. This step will build the image for your container.
    
    ```bash
    docker build -t your_image_name .
    ```
    
4. **Add a deployment step:**
    
    Next, include a step to run the "docker run" command, launching a container using the image created in the previous step.
    
    ```bash
    docker run -d -p 8080:8080 your_image_name
    ```
    

**Task-02: Managing Docker Compose**

Now, let's raise the bar by orchestrating multiple containers defined in a Docker Compose file using Jenkins Freestyle Projects.

**Solution:**

1. **Create a Jenkins project:**
    
    Start by creating a new Jenkins project dedicated to managing your Docker Compose setup.
    
2. **Configure the project:**
    
    Within the project configuration, specify the necessary parameters to execute the Docker Compose commands.
    
    ```bash
    pipeline {
        agent any
        stages {
            stage('Deploy') {
                steps {
                    sh 'docker-compose up -d'
                }
            }
            stage('Cleanup') {
                steps {
                    sh 'docker-compose down'
                }
            }
        }
    }
    ```
    
3. **Start containers:**
    
    Add a build step to run "docker-compose up -d," starting the containers defined in your Docker Compose file.
    
    ```bash
    docker-compose up -d
    ```
    
4. **Implement cleanup:**
    
    To ensure proper resource management, set up a cleanup step to execute "docker-compose down," halting and removing the containers defined in the Compose file.
    
    ```bash
    docker-compose down
    ```
    

**Conclusion:**

In today's #90DaysOfDevOps challenge, we've embarked on a journey to master Jenkins Freestyle Projects—an integral tool for DevOps practitioners. From automating Docker container builds to orchestrating complex deployments with Docker Compose, we've covered significant ground.

Remember, continuous learning and hands-on practice are the keys to unlocking your full potential as a DevOps engineer. Keep exploring, keep innovating, and most importantly, keep pushing your limits.

Feel free to share your insights and experiences on LinkedIn using the #90DaysOfDevOps Challenge. Let's inspire and empower each other on this remarkable journey!

Stay tuned for more exciting challenges ahead. Until next time, keep thriving in the world of DevOps! Ending this with a quote

> Build jobs in Jenkins are the heartbeat of automation, pulsing life into the software development process with each executed task.

Happy Learning.