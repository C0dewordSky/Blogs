---
title: "Day 16 - Docker Basics"
seoTitle: "Docker Basics"
datePublished: Sun Feb 11 2024 09:09:19 GMT+0000 (Coordinated Universal Time)
cuid: clshaafk5000309ie3ckv9xcr
slug: day-16-docker-basics
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/HSACbYjZsqQ/upload/adf8fec549ee83a2608d558e99965cb8.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1707642514370/5e1fb1fb-7772-47c5-82bf-1b9956977dd8.png
tags: docker, aws, kubernetes, devops, hashnode, 2articles1week, technical-writing-1, docker-images, devops-articles, devops-journey, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge, devopscommunity

---

## Introduction

Welcome DevOps enthusiasts and learners. In this blog we're taking a step forward into the world of containerization and Docker comes out out be the most popular amongst all of the tools. So we'll understand what containerization is, its usage and its benefits. We'll dive into Docker and understand the Installation Process and go through some of the most common commands. So without any more delay, let's just Jump into it.

## Container and Containerization

![](https://miro.medium.com/v2/resize:fit:1400/1*cgaBv9WOLVzihnSxZlUmmQ.png align="center")

### What is Container?

A container is an executable software package that contains the entire application, from code to runtime to essential packages and dependencies that are required for smooth functioning of the application.

It is lightweight and most importantly scalable which makes it the best option for scaling, distributing, transporting or running the application in any environment.

### What is Containerization?

Containerization is a method of packaging an entire application and its dependencies into a container. This containerized application can then be run on any platform or Operating Systems.

These containers encapsulate everything the application needs to run, including libraries, binaries, and configuration files, ensuring consistency and reliability across different environments.

The most famous containerization tool is Docker and Kubernetes is used for container Orchestration.

## Docker

![](https://www.linode.com/docs/guides/when-and-why-to-use-docker/when-why-docker_hu4feaf90a111e9478f96c85283e8439d5_45534_694x0_resize_q71_bgfafafc_catmullrom.jpg align="center")

Docker is a software that is used for containerizing application. It is an Open-Source application and is widely used for its user-friendly feature and extensive support. It provides developers and DevOps teams with an easy way to package, distribute, and manage applications within containers.

Docker simplifies the process of creating and managing containers by providing a set of tools and APIs that abstract away much of the complexity involved in containerization.

Some of Docker's most useful features include versioning, layering, and networking, which further enhance its capabilities for containerization.

Read More about Docker, [Here](https://docs.docker.com/get-started/overview/#:~:text=Docker%20uses%20a%20client%2Dserver,to%20a%20remote%20Docker%20daemon.).

### How Docker Works? A short and Quick Overview

![](https://miro.medium.com/v2/resize:fit:964/1*4wxxEtEJIIuFt3HSAK2Wfw.png align="center")

Docker works by leveraging operating system-level virtualization features, primarily using containerization technology provided by the Linux kernel. Here's a simplified overview of how Docker works in the background:

1. **Docker Container**: Think of a Docker container as a small self-contained box that holds everything you need to run an application—code, libraries, and settings.
    
2. **Docker Image**: Before you can create a container you need a blueprint called an image. It’s like having a template for your character.
    
3. **Docker Daemon**: This is similar to Docker’s manager. It runs in the background all the time, making sure everything works properly in Docker.
    
4. **Docker Client**: Think of this as a way to talk to your Docker Daemon. You give it commands like "create this image" or "move this object".
    
5. **Building and Running**: You use Docker to build an image from a blueprint (<mark>Dockerfile</mark>) and then run it to build the container.
    
6. **Isolation**: Each character is like their own little world. They cannot be seen or tampered with from one another, making it safer to run multiple applications on the same machine.
    
7. **Networking**: Docker helps containers talk to each other or the outside world, so they can work together or connect to the Internet.
    
8. **Storage**: Docker can store data in containers that need to be associated with it, such as databases or user uploads, in a way that is easy to manage and back up.
    

## Commands

Here are some of the most important Docker Commands:

1. **To run a Docker Container**:
    
    ```bash
    docker run <image_name>
    ```
    
2. **To run a Docker Container in detached mode (in the background)**:
    
    ```bash
    docker run -d <image_name>
    ```
    
3. **To run a Docker Container with a specific name**:
    
    ```bash
    docker run --name <container_name> <image_name>
    ```
    
4. **To run a Docker Container and expose ports**:
    
    ```bash
    docker run -p <host_port>:<container_port> <image_name>
    ```
    
5. **To run a Docker Container with environment variables**:
    
    ```bash
    docker run -e <key>=<value> <image_name>
    ```
    
6. **To run a Docker Container with volumes**:
    
    ```bash
    docker run -v <host_path>:<container_path> <image_name>
    ```
    
7. **To run a Docker Container with interactive mode (to enter the container's shell)**:
    
    ```bash
    docker run -it <image_name>
    ```
    
    \-it: Interactive Terminal
    
8. **To run a Docker Container with resource constraints**:
    
    ```bash
    docker run --cpu-shares=<value> --memory=<value> <image_name>
    ```
    
9. List images in Docker
    
    ```bash
    docker images
    ```
    
10. To see the running containers
    
    ```bash
    docker ps
    ```
    
11. To see all the containers, running or stopped
    
    ```bash
    docker ps -a
    ```
    

Remember to replace `<image_name>` with the name of the Docker image you want to run, and adjust any additional options as needed for your specific use case.

Read In detail, [Here](https://docs.docker.com/engine/reference/commandline/docker/).

## Hands-on Practice

### Tasks

* Use the `docker run` command to start a new container and interact with it through the command line. \[Hint: docker run hello-world\]
    
* Use the `docker inspect` command to view detailed information about a container or image.
    
* Use the `docker port` command to list the port mappings for a container.
    
* Use the `docker stats` command to view resource usage statistics for one or more containers.
    
* Use the `docker top` command to view the processes running inside a container.
    
* Use the `docker save` command to save an image to a tar archive.
    
* Use the `docker load` command to load an image from a tar archive.
    

These tasks involve simple operations that can be used to manage images and containers.

## Solution:

1. Run Docker command and Interact with it
    
    ```bash
    docker run hello-world
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707640707616/21b3b30c-fcab-4f0b-be57-c5b52452f0d8.png align="center")
    
2. Docker Inspect
    
    ```bash
    docker inspect <image_name> 
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707640792238/c38f861c-2b46-4ea6-bcb2-b25b5c3f134c.png align="center")
    
3. Docker Port Mapping
    
    We map the ports to port 80
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707640906298/96a8c0c0-d5ad-468f-a0c6-f4283c9c8984.png align="center")
    
4. Docker Stats to check the stats of the running container
    
    ```bash
    docker stats container_name1 container_name2 
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707641038324/9eb03be6-f355-42de-9190-d3f922cc672e.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707641056599/b36f60f4-6634-4331-8d0c-5fd076aba1fc.png align="center")
    
    This Will appear and show stats of all the "Running" Containers.
    
5. View the processes running inside a container:
    
    ```bash
    docker top <container_id>
    ```
    
6. Save an image to a tar archive:
    
    ```bash
    docker save -o <output_file.tar> <image_name>
    ```
    
7. Load an image from a tar archive:
    
    ```bash
    docker load -i <input_file.tar>
    ```
    

## Conclusion

And that wraps up today's blog! We covered a range of Docker commands, from the basics to more advanced ones, and even got our hands dirty with some practical exercises. Throughout, we gained a solid understanding of containers and containerization, while also peering into the inner workings of Docker.

Join me again tomorrow as we delve even deeper into Docker, exploring its commands and functionalities in greater detail. I trust that today's insights have enriched your learning journey. Until next time, stay curious and keep exploring!

Ending this with a quote

> Believe you can and you're halfway there. - Theodore Roosevelt

Happy Learning.