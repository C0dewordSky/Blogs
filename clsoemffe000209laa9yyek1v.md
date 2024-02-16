---
title: "Day 21 - Docker Interview Questions"
seoTitle: "Docker Interview Questions"
datePublished: Fri Feb 16 2024 08:45:00 GMT+0000 (Coordinated Universal Time)
cuid: clsoemffe000209laa9yyek1v
slug: day-21-docker-interview-questions
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1708072235425/accdbbab-20a0-4188-8ce5-1f2f3ce9bad8.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1708073078086/92d4ef59-5596-4f87-82d6-0140b24e0d19.png
tags: interview, docker, aws, development, kubernetes, developer, devops, 2articles1week, technical-writing-1, docker-images, devops-articles, devops-journey, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge

---

## Introduction

Welcome DevOps enthusiasts and Learners. This blog will be a very interesting one as we'll go through some of the most important DevOps Interview Question. Covering from basic till some advanced concepts, I got you covered. I'll be giving you short answers that'll help you for quick revision of the topics.

But before moving forward, I request you to write a blog and answer all these questions from your own understanding and don't forget to share on on relevant social media sites like LinkedIn or Twitter. So without any further delay, let's just jump into learning.

## Interview Questions

1. What is the Difference between an Image, Container and Engine?
    
2. What is the Difference between the Docker command COPY vs ADD?
    
3. What is the Difference between the Docker command CMD vs RUN?
    
4. How Will you reduce the size of the Docker image?
    
5. Why and when to use Docker?
    
6. Explain the Docker components and how they interact with each other.
    
7. Explain the terminology: Docker Compose, Docker File, Docker Image, Docker Container?
    
8. In what real scenarios have you used Docker?
    
9. Docker vs Hypervisor?
    
10. What are the advantages and disadvantages of using docker?
    
11. What is a Docker namespace?
    
12. What is a Docker registry?
    
13. What is an entry point?
    
14. How to implement CI/CD in Docker?
    
15. Will data on the container be lost when the docker container exits?
    
16. What is a Docker swarm?
    
17. What are the docker commands for the following:
    
    a) View running containers
    
    b) Command to run the container under a specific name
    
    c) Command to export a docker
    
    d) Command to import an already existing docker image
    
    e) Commands to delete a container
    
    f) Command to remove all stopped containers, unused networks, build caches, and dangling images?
    
18. What are the common docker practices to reduce the size of Docker Image?
    

## Solution

1. 1. **Difference between Image, Container, and Engine**:
        
        * **Image**: A template with instructions to create a container. It includes a filesystem and parameters.
            
        * **Container**: A runtime instance of an image. It encapsulates an application and its dependencies.
            
        * **Engine**: The core of Docker that creates and manages containers. It's responsible for building, running, and distributing containers.
            
    2. **Difference between Docker** `COPY` vs `ADD` command:
        
        * `COPY`: Copies files from the host into the container file system.
            
        * `ADD`: Similar to `COPY` but with additional features like auto-extracting compressed files and downloading files from URLs.
            
    3. **Difference between Docker** `CMD` vs `RUN` command:
        
        * `CMD`: Specifies the command to run when the container starts.
            
        * `RUN`: Executes commands during the image build process.
            
    4. **Reducing Docker Image Size**:
        
        * Use a slim base image.
            
        * Minimize layers by combining commands.
            
        * Remove unnecessary dependencies and files.
            
        * Utilize multi-stage builds.
            
        * Optimize Dockerfile instructions.
            
    5. **Why and When to Use Docker**:
        
        * Provides consistent environments.
            
        * Facilitates easy deployment and scaling.
            
        * Enables microservices architecture.
            
        * Simplifies development workflows.
            
        * Ideal for CI/CD pipelines.
            
    6. **Explanation of Docker Terminology**:
        
        * **Docker Compose**: Tool for defining and running multi-container Docker applications.
            
        * **Dockerfile**: A text file containing instructions to build a Docker image.
            
        * **Docker Image**: A lightweight, standalone, executable package that includes everything needed to run a piece of software.
            
        * **Docker Container**: A runtime instance of a Docker image.
            
    7. **Real Scenarios of Docker Usage**:
        
        * Application deployment.
            
        * Microservices architecture.
            
        * Continuous integration and deployment.
            
        * Testing and development environments.
            
    8. **Docker vs Hypervisor**:
        
        * Docker utilizes OS-level virtualization, while hypervisors create full virtual machines.
            
        * Docker containers share the host OS kernel, making them lightweight and efficient.
            
        * Hypervisors offer stronger isolation but with higher overhead.
            
    9. **Advantages and Disadvantages of Docker**:
        
        * *Advantages*: Portability, scalability, rapid deployment, resource efficiency.
            
        * *Disadvantages*: Security concerns, complexity in managing networking, learning curve.
            
    10. **Docker Namespace**:
        
        * A mechanism to isolate system resources such as processes, network interfaces, and filesystems.
            
    11. **Docker Registry**:
        
        * A repository for storing and distributing Docker images.
            
    12. **Entry Point**:
        
        * The command or script that runs when a container starts.
            
    13. **Implementing CI/CD in Docker**:
        
        * Use Docker to create consistent environments for testing and deployment.
            
        * Utilize Docker Compose or Kubernetes for orchestration.
            
        * Integrate Docker with CI/CD tools like Jenkins or GitLab CI.
            
    14. **Data Persistence in Docker**:
        
        * Data in a container's writable layer is lost when the container exits.
            
        * Use volumes or bind mounts to persist data outside the container.
            
    15. **Docker Swarm**:
        
        * Docker's native clustering and orchestration tool for managing multiple Docker hosts.
            
    16. **Common Docker Commands**:
        
        * *View running containers*: `docker ps`
            
        * *Run container with specific name*: `docker run --name <container_name>`
            
        * *Export a Docker image*: `docker save`
            
        * *Import an existing Docker image*: `docker load`
            
        * *Delete a container*: `docker rm`
            
        * *Remove stopped containers, unused networks, build caches, dangling images*: `docker system prune`
            
    17. **Common Practices to Reduce Docker Image Size**:
        
        * Use smaller base images.
            
        * Minimize the number of layers.
            
        * Remove unnecessary dependencies.
            
        * Optimize Dockerfile instructions.
            

## Conclusion

These questions cover a range of topics related to Docker, including its terminology, usage, comparison with other technologies, practical implementation, and best practices. They are designed to assess an individual's understanding and proficiency in Docker and are valuable for DevOps interviews. It will greatly help you in your next DevOps Interview.

*Write a Blog and share it on LinkedIn. Ending this with a quote*

> Believe you can and you're halfway there. - Theodore Roosevelt

Happy Learning.