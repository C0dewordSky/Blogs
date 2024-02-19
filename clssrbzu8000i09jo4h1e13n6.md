---
title: "Day 24 - Jenkins CI/CD Project Part - 1"
seoTitle: "Jenkins CI/CD Project Part - 1"
datePublished: Mon Feb 19 2024 09:51:53 GMT+0000 (Coordinated Universal Time)
cuid: clssrbzu8000i09jo4h1e13n6
slug: day-24-jenkins-cicd-project-part-1
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1708336120086/b5893352-9f45-4936-be7a-3d00e0f2df84.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1708336297979/6776321e-7a92-4a06-9cdd-a1204a17b36d.png
tags: cloud, docker, aws, developer, cloud-computing, devops, hashnode, jenkins, pipeline, ci-cd, technical-writing-1, devops-articles, devops-journey, trainwithshubham, devopscommunity

---

## Introduction

**NOTE: This is Part - 1 of the Project. Part 2 will be uploaded tomorrow.**

**I**n the arena of contemporary software development, Continuous Integration and Continuous Delivery (CI/CD) have become critical practices. By automating the build, test, and deployment processes, CI/CD pipelines ensure the rapid and reliable delivery of software updates.

In this blog post, we will embark on a journey to create a robust CI/CD pipeline for a Node.Js application using Jenkins, Docker, and GitHub integration.

## Day 23 Recap: Understanding Jenkins CI/CD

Before diving into the project, let's recap the concepts covered in Day 23. Jenkins is a widely-used open-source automation server that enables CI/CD processes. It allows developers to automate various stages of the software development lifecycle, including building, testing, and deploying applications. Key concepts covered include:

1. Setting up Jenkins on a server.
    
2. Creating Jenkins jobs to automate tasks.
    
3. Integrating Jenkins with GitHub for version control.
    
4. Configuring webhooks for triggering Jenkins builds upon code modifications.
    

## The Jenkins CI/CD Project

Repo: https://github.com/LondheShubham153/node-todo-cicd

### Task 01:

GitHub Integration and Jenkins Setup To kickstart the project, we need to fork the provided repository and establish a connection between Jenkins and GitHub. This involves setting up a webhook on GitHub to trigger Jenkins builds upon code commits.

* **Step 1:** Fork the Repository
    
* **Step 2:** Configure GitHub Integration
    
    1. Navigate to Jenkins and create a new freestyle project.
        
    2. Configure the GitHub project URL to point to your forked repository.
        
    3. Set up GitHub webhook to trigger builds on push events.
        
    4. Define build triggers and configure Jenkins to pull code from the GitHub repository.
        

### Task 02: Dockerizing the Node.Js Application

With the GitHub integration in place, it's time to containerize the Node.Js application using Docker Compose.

* **Step 1:** Docker Compose File Creation
    
    * Create a Docker Compose file (`docker-compose.yml`) to define the application's services and their configurations.
        
        ```bash
        version: '3'
        services:
          web:
            image: node:latest
            ports:
              - "3000:3000"
            volumes:
              - ./app:/app
            working_dir: /app
            command: npm start
        ```
        
* **Step 2:** Running the Application with Docker Compose
    
    * Launch the application by running the command: `docker-compose up -d`
        
        ```bash
        docker-compose up -d
        ```
        
* **Step 3:** Accessing the Application
    
    * Once the containers are up and running, access the Node.Js application by navigating to [http://localhost:3000](http://localhost:3000) in a web browser.
        

## Insights

Through this assignment, we have achieved the following goals:

1. Established a Seamless CI/CD Pipeline: By integrating Jenkins with GitHub and automating the build process, we have created a robust CI/CD pipeline for our Node.Js application.
    
2. Containerized the Application: Docker and Docker Compose have been instrumental in containerizing our application, making it portable and scalable across different environments.
    
3. Learned About Webhooks: Understanding how webhooks work in GitHub and configuring them to trigger Jenkins builds provided valuable insights into automating workflows.
    

## **Conclusion**

In this blog post, we embarked on a journey to create a continuous CI/CD pipeline for a Node.Js application using Jenkins, Docker, and GitHub integration. We learned how to set up Jenkins jobs, configure webhooks, and containerize our application with Docker Compose.

By automating the build, test, and deployment processes, we have empowered ourselves to deliver software updates quickly and reliably. Embracing CI/CD practices fosters a culture of collaboration, agility, and continuous improvement in software development.

**NOTE:** This blog post is a blueprint of creating your own project and the complete project will be out on my blog in a few days. The steps outlined may vary depending on individual setups and configurations.

**Pro Tip:** Always refer to official documentation for the latest guidelines and best practices.

Ending this with a quote

> In the realm of software development, our journey towards excellence begins with embracing change and mastering the art of continuous improvement.

Happy Learning.