---
title: "Day 19 - Docker Volume and Networking"
seoTitle: "Docker Volume and Networking"
datePublished: Wed Feb 14 2024 08:39:27 GMT+0000 (Coordinated Universal Time)
cuid: clsljjlc9000309iecgyndqm4
slug: day-19-docker-volume-and-networking
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707899935434/3f9b9e75-246c-4776-b4fc-b2140ac40910.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1707899819162/e3ee8e31-f624-4482-a525-d8f99b08a37b.png
tags: cloud, docker, aws, kubernetes, devops, networking, 2articles1week, technical-writing-1, devops-articles, devops-journey, docker-volume, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge, devopscommunity

---

## Introduction

Welcome DevOps enthusiasts and learners. In this blog we're delving deep into docker and learning some more important concepts that needs to be mastered in order to excel in your career. Today we're gonna learn and work on Docker Volumes and Docker Networking. It's one of the most important concepts to master in order to enable multiple containers talk to each other.

Along with that our tradition, of solving hands on questions, will remain the same and by the end of this blog we'll be working on the concepts to master it. SO without any further ado, let's begin.

## Docker Volume

![](https://docs.docker.com/storage/images/types-of-mounts-volume.webp?w=450&h=300 align="center")

What is a volume? You might have this question in your mind. In simple words, volume is storage or memory space where data can be stored persistently.

A Docker Volume is a special directory within a container that exits outside of a container's filesystem. It provides persistent storage for data independent of the lifecycle of the container.

### Why use Docker Volume?

In Docker container, the data stored is not persistent. That means all the data in the container gets destroyed when the container is restarted.

In order to deal with this and keep the data safe, Docker came up with the concept of Docker Volume where we can mount the data inside of a container to a special directory on the host filesystem for persistent data storage and to keep the data safe and secure even after the container is stopped or killed.

### Benefits of Docker Volume:

1. **Persistent volume:** Volumes provide a way to store data persistently outside the container's filesystem, ensuring that data survives container restarts, upgrades, or deletions.
    
2. **Performance Optimization:** Docker volumes can be configured with different storage drivers to optimize performance based on specific use cases and storage requirements. For example using High-Performance storage.
    
3. **Data sharing with other containers:** Volumes can be shared among multiple containers, allowing them to access and manipulate shared data. This is useful for scenarios where multiple containers need access to the same data or for implementing communication mechanisms between containers.
    
4. **Backup and Restore:** Volumes can be backed up and restored independently of containers, providing a straightforward mechanism for data backup and recovery. This is crucial for maintaining data integrity and ensuring business continuity in case of failures.
    
5. **Separation of concern:** By storing data in volumes separate from the container's filesystem, you can separate concerns between the application code and its data. This makes it easier to manage and update applications without worrying about data loss or corruption.
    

### Docker Volume Commands:

Here are some commonly used Docker commands related to volumes:

1. **Create a Volume**:
    
    ```bash
    docker volume create <volume_name>
    ```
    
2. **List Volumes**:
    
    ```bash
    docker volume ls
    ```
    
3. **Inspect a Volume**:
    
    ```bash
    docker volume inspect <volume_name>
    ```
    
4. **Remove a Volume**:
    
    ```bash
    docker volume rm <volume_name>
    ```
    
5. **Remove Unused Volumes**:
    
    ```bash
    docker volume prune
    ```
    
6. **Mount a Volume to a Container**:
    
    ```bash
    docker run -v <volume_name>:<container_mount_path> <image_name>
    
    #Example
    docker run -d --name myapp -v myapp_data:/app/data myapp_image
    ```
    
    \-d: detached mode or background mode
    
    \-v: Declaring volume and mounting it
    
7. **Mount a Named Volume to a Container**:
    
    ```bash
    docker run -v <volume_name>:<container_mount_path> <image_name>
    ```
    
    **NOTE:** Mount is a process of linking container data to a local filesystem directory.
    
8. **Mount a Host Directory as a Volume**:
    
    ```bash
    docker run -v <host_directory>:<container_mount_path> <image_name>
    ```
    
9. **Mount a Host Directory as a Named Volume**:
    
    ```bash
    docker run -v <volume_name>:<container_mount_path> -v <host_directory>:<container_mount_path> <image_name>
    ```
    
10. **Inspect Mounts for a Container**:
    

```bash
docker inspect <container_id_or_name>
```

## Docker Networking

![](https://miro.medium.com/v2/resize:fit:1400/0*nLE3V2rA26TY3T03.png align="center")

Docker Networking refers to the mechanism docker offers for the containers to communicate between each other and connect and communicate with external network.

Docker networking allows containers to be connected to each other and to other networked resources such as the host machine, other containers, or external networks like the internet.

It enables seamless communication and data exchange between containers, facilitating the construction of complex distributed applications.

### Some Key Concepts:

1. **Port Mapping**: Docker allows you to map ports on the host machine to ports exposed by containers. This enables external access to services running inside containers.
    
2. **Service Discovery and Load Balancing**: Docker provides built-in features for service discovery and load balancing in Docker Swarm mode.
    
3. **User-defined Bridge Networks**: Docker allows users to create custom bridge networks to segment container communication within the Docker host. Containers attached to the same user-defined bridge network can communicate with each other but are isolated from containers attached to other bridge networks.
    

### Some Components of Docker Networking

1. **Bridge Network**: When Docker is installed, it creates a default bridge network called `bridge`. Containers attached to this network can communicate with each other using container names as hostnames. <mark>This network provides internal connectivity within a single Docker host.</mark>
    
2. **Host Network**: Using the `host` network mode, a container shares the network namespace with the Docker host, effectively using the host's networking stack. This means that the container can directly access services running on the host's network interfaces.
    
3. **Overlay Network**: Overlay networks enable communication between containers running on different Docker hosts.
    
4. **Macvlan Network**: This enables containers to directly access external resources on the network.
    

Read More about Docker Networking, Here.

## Networking Commands

Here are some commonly used Docker commands related to networking:

1. **List Networks**:
    
    ```bash
    docker network ls
    ```
    
2. **Inspect a Network**:
    
    ```bash
    docker network inspect <network_name>
    ```
    
3. **Create a Network**:
    
    ```bash
    docker network create <network_name>
    ```
    
4. **Disconnect a Container from a Network**:
    
    ```bash
    docker network disconnect <network_name> <container_name_or_id>
    ```
    
5. **Remove a Network**:
    
    ```bash
    docker network rm <network_name>
    ```
    
6. **Prune Unused Networks**: Remove all unused network.
    
    ```bash
    docker network prune
    ```
    
7. **Inspect Container's Networks**:
    
    ```bash
    docker inspect <container_name_or_id>
    ```
    
8. **Create a Container with a Specific Network**:
    
    ```bash
    docker run --network=<network_name> <image_name>
    ```
    
9. **Connect a Container to Multiple Networks**:
    
    ```bash
    docker network connect <network_name> <container_name_or_id>
    
    #Example 
    docker network connect frontend web_server
    docker network connect backend web_server
    ```
    

## Hands On Practice

* Create a multi-container docker-compose file which will bring *UP* and bring *DOWN* containers in a single shot ( Example - Create application and database container )
    

*hints:*

* Use the `docker-compose up` command with the `-d` flag to start a multi-container application in detached mode.
    
* Use the `docker-compose scale` command to increase or decrease the number of replicas for a specific service. You can also add [`replicas`](https://stackoverflow.com/questions/63408708/how-to-scale-from-within-docker-compose-file) in deployment file for *auto-scaling*.
    
* Use the `docker-compose ps` command to view the status of all containers, and `docker-compose logs` to view the logs of a specific service.
    
* Use the `docker-compose down` command to stop and remove all containers, networks, and volumes associated with the application
    

## Task-2

* Learn how to use Docker Volumes and Named Volumes to share files and directories between multiple containers.
    
* Create two or more containers that read and write data to the same volume using the `docker run --mount` command.
    
* Verify that the data is the same in all containers by using the docker exec command to run commands inside each container.
    
* Use the docker volume ls command to list all volumes and docker volume rm command to remove the volume when you're done.
    

**You can use this task as *Project* to add in your resume.**

## Solution

**NOTE: A Separate blog on this project will come where I will be solving and sharing this project with repository in detail.**

Here's b brief blueprint of the solution :

**TASK 1:**

For Task-1, where you're required to create a multi-container Docker Compose file and manage containers using `docker-compose` commands, here are the steps:

1. **Create a Docker Compose file** (`docker-compose.yml`):
    
    ```yaml
    version: '3'
    
    services:
      app:
        image: your-app-image
        volumes:
          - app_data:/app/data
        # Add any other configurations for your application container
    
      database:
        image: your-database-image
        volumes:
          - db_data:/var/lib/mysql
        # Add any other configurations for your database container
    
    volumes:
      app_data:
      db_data:
    ```
    
2. **Start Containers with Docker Compose**:
    
    ```bash
    docker-compose up -d
    ```
    
3. **Scaling Containers (Optional)**: If you want to scale the number of replicas for a specific service, you can use `docker-compose scale`:
    
    ```bash
    docker-compose scale app=3
    ```
    
4. **View Container Status**:
    
    ```bash
    docker-compose ps
    ```
    
5. **View Logs**:
    
    ```bash
    docker-compose logs app
    ```
    
6. **Stop and Remove Containers, Networks, and Volumes**:
    
    ```bash
    docker-compose down
    ```
    

**TASK 2 :**

To accomplish Task-2 using Docker volumes and named volumes, you can follow these steps:

1. **Create Docker Volumes**:
    
    ```bash
    docker volume create app_data
    docker volume create db_data
    ```
    
2. **Start Containers with Volumes**:
    
    ```bash
    docker run -d --name app_container --mount source=app_data,target=/app/data your-app-image
    docker run -d --name db_container --mount source=db_data,target=/var/lib/mysql your-database-image
    ```
    
3. **Verify Data Consistency**: You can verify that the data is consistent between containers by executing commands within each container:
    
    ```bash
    # For app container
    docker exec -it app_container sh
    # Now you're inside the app container, you can check the contents of /app/data
    
    # For db container
    docker exec -it db_container sh
    # Now you're inside the db container, you can check the contents of /var/lib/mysql
    ```
    
4. **List Volumes**:
    
    ```bash
    docker volume ls
    ```
    
5. **Remove Volume (when done)**:
    
    ```bash
    docker volume rm app_data
    docker volume rm db_data
    ```
    

This is a blueprint of how you can solve the tasks. Along with this I'll be sharing a separate solution blog, completing the Project in detail and you can follow along and add that to your resume.

## Conclusion

With a wealth of information on Docker volumes and networking at our fingertips, this blog has undoubtedly expanded our understanding of these crucial elements in DevOps.

We have gained insight into the pivotal role of volumes in preserving data and how networking enables smooth communication between containers and external entities, laying the foundation for streamlined application building and release.

Through hands-on demonstrations and commands, we have sharpened our abilities and positioned ourselves for success in our professional endeavors. So, let's embrace further exploration, experimentation, and growth in the ever-evolving realm of DevOps.

I hope this blog added value to your learning. Ending this with a quote

> Mastering Docker volumes and networking is not just about understanding technology; it's about building bridges between containers and possibilities.

Happy Learning.