---
title: "Day 18 - Docker and Docker Project Part -2"
seoTitle: "Docker Compose and YAML "
datePublished: Tue Feb 13 2024 06:41:01 GMT+0000 (Coordinated Universal Time)
cuid: clsjzvfk300050ale49j9bp7u
slug: day-18-docker-and-docker-project-part-2
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707799484975/d9a83634-2e39-4d58-b9d1-5557a301252d.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1707806428558/3d9e617c-3a66-42af-b0d3-04e5cbaba4f8.png
tags: docker, aws, kubernetes, devops, hashnode, docker-compose, 2articles1week, technical-writing-1, docker-images, devops-articles, devops-journey, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge, devopscommunity

---

## Introduction

Welcome DevOps enthusiasts and learners. In this blog we're delving deep and learning few of the major concepts in Docker. We'll be diving into Docker compose and Understand the basics of writing a YAML configuration file. YAML is one of the most important script a DevOps engineer need to master and We'll get our hands dirty with practicing the concepts by the end of this blog. So without any further delay, Let's just jump into learning.

## Docker Compose

In the last blog we saw Dockerfile for creating an Image and running a container. But what if we want to run an application having multiple containers interacting with each other?

That's where Docker Compose comes to your rescue. It is a multi-container management tool provided by Docker to run multi-container application, Network efficiently and collaboration.

### Working:

Docker compose utilizes the power of YAML to its full potential. A user can write a configuration file that contains all the information about the application containers and Docker Compose will go through it and perform tasks accordingly.

Docker Compose provides a set of commands that allow users to manage their multi-container applications based on the configuration defined in the YAML file. This includes commands to start, stop, build, and manage the containers, as well as to view logs and other information about the application.

An Example YAML configuration file:

```bash
version: '3'
services:
  db:
     image: mysql
     container_name: mysql_db
     restart: always
     environment:
        - MYSQL_ROOT_PASSWORD="secret"
  web:
    image: apache
    build: .
    container_name: apache_web
    restart: always
    ports:
      - "8080:80"
```

This YAML configuration file defines services i.e. the containers. The db and web are containers.

With Docker Compose, you can easily define the relationships and dependencies between containers, specify environment variables, expose ports, and mount volumes, all within a declarative configuration file.

This makes it much easier to collaborate on multi-container applications, as you can share the `docker-compose.yml` file along with the application code, enabling others to quickly spin up the entire application environment with a single command.

## YAML

![](https://clarusway.com/wp-content/uploads/2021/01/docker-compose-yml-1024x568.png align="center")

Yet another Markup language. YAML is a human-readable data serialization language commonly used for writing a configuration file. It is understandable by both humans and Machine.

It uses "Indentation" to represent nest and data structures.

Components in a YAML file:

| Component | Explanation |
| --- | --- |
| Scalars | Scalars are single atomic values in YAML. They include strings, numbers, booleans, and null values. Scalars do not require any special formatting and are represented directly. |
| Sequences (Arrays)or(List) | Sequences, also known as arrays or lists, allow you to group multiple values together in a specific order. They are denoted by a dash (`-`) followed by the sequence items. |
| Mappings (Objects) | Mappings, also known as objects or dictionaries, allow you to associate key-value pairs. They are denoted by key-value pairs separated by a colon (`:`) and are usually indented. |
| Comments | Comments in YAML are preceded by the `#` symbol. They are used to add explanatory notes or annotations within the configuration files. |
| Indentation | YAML uses indentation to represent nesting and structure. The level of indentation indicates the hierarchy of elements, with each level typically indented by two spaces or a tab. |
| Anchors & Aliases | Anchors (`&`) allow you to create named references to specific nodes in YAML data. Aliases (`*`) are used to refer back to these anchors, enabling reuse of data across the document. |

These components form the basic building blocks of YAML syntax, allowing us to represent complex data structures in a human-readable and concise manner.

**Examples:**

1. **Scalers** : (Strings, Numbers, Booleans, Null)
    
    ```bash
    name: Aakash
    age: 25
    is_student: false
    description: null
    ```
    
2. **Lists**: Represented by a " - " .
    
    ```bash
    fruits: 
      - apple
      - banana
      - guava
      - mango 
    ```
    
3. **Mapping**: Key-Value pair
    
    ```bash
    person:
      name: Alice
      age: 25
      address:
        city: New York
        zip_code: 10001
    ```
    
4. **Comments**: These are represented by a " # " symbol.
    
    ```bash
    # This is a comment 
    ```
    
5. **Indentation**: Hierarchical structure indicated by indentation.
    
    ```bash
    person:
      name: Alice
      age: 25
      address:
        city: New York
        zip_code: 10001
    ```
    
    The above example means:
    
    "**<mark>person</mark>**" is Parent and "**<mark>name, age and address</mark>**" are Child
    
    "**<mark>address</mark>**" is Parent and "**<mark>city, zip_code"</mark>** are child.
    

## Docker Compose Commands

Here's how each Docker Compose command works with an example:

1. **docker-compose up**:
    
    ```bash
    docker-compose up
    ```
    
    This command starts up your Docker Compose-defined application. It creates and starts all the containers defined in your `docker-compose.yml` file.
    
2. **docker-compose down**:
    
    ```bash
    docker-compose down
    ```
    
    This command stops and removes all the containers, networks, and volumes defined in your `docker-compose.yml` file. It's the opposite of `docker-compose up`.
    
3. **docker-compose build**:
    
    ```bash
    docker-compose build
    ```
    
    This command builds or rebuilds the images for your services. It's useful when you've made changes to your Dockerfiles or any other build context, and you want to update the images.
    
4. **docker-compose start**:
    
    ```bash
    docker-compose start
    ```
    
    This command starts the containers for your services, but it doesn't create new ones. It's useful when you've stopped the containers using `docker-compose stop` and want to start them again.
    
5. **docker-compose stop**:
    
    ```bash
    docker-compose stop
    ```
    
    This command stops the running containers for your services but doesn't remove them. It's useful when you want to stop your application temporarily.
    
6. **docker-compose restart**:
    
    ```bash
    docker-compose restart
    ```
    
    This command restarts all the containers in your Docker Compose application. It's useful when you've made changes to your configuration files or environment variables.
    
7. **docker-compose ps**:
    
    ```bash
    docker-compose ps
    ```
    
    This command shows the running containers for your Docker Compose application, along with their status.
    
8. **docker-compose logs**:
    
    ```bash
    docker-compose logs
    ```
    
    This command shows the logs for all the containers in your Docker Compose application. You can use the `-f` flag to follow the logs in real-time.
    
9. **docker-compose exec**:
    
    ```bash
    docker-compose exec web_server ls -l /app
    ```
    
    This command allows you to run commands inside a running container. For example, `docker-compose exec <service_name> <command>`.
    
10. **docker-compose down -v**:
    
    ```bash
    docker-compose down -v
    ```
    
    This command stops and removes containers, networks, and volumes defined in your `docker-compose.yml` file. It also removes any named volumes defined in the `volumes` section of the `docker-compose.yml` file and anonymous volumes attached to containers.
    

## Hands On Practice

### Task -1

Learn how to use the docker-compose.yml file, to set up the environment, configure the services and links between different containers, and also to use environment variables in the docker-compose.yml file.

[Sample docker-compose.yaml file](https://github.com/C0dewordSky/90DaysOfDevOps/blob/master/2023/day18/docker-compose.yaml)

### Task-2

* Pull a pre-existing Docker image from a public repository (e.g. Docker Hub) and run it on your local machine. Run the container as a non-root user
    
* Make sure you reboot instance after giving permission to user.
    
* Inspect the container's running processes and exposed ports using the docker inspect command.
    
* Use the docker logs command to view the container's log output.
    
* Use the docker stop and docker start commands to stop and start the container.
    
* Use the docker rm command to remove the container when you're done.
    

## Solution

### Task -2

1. Running a container as a non root user
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707805652831/da1580bd-f62d-4feb-9912-ea3786e685bb.png align="center")
    
    \-d: stands for detached mode i.e. container will run in the background.
    
2. Inspect the container's running processes and exposed ports using the docker inspect command. Using `docker inspect` command.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707805747651/565d6b39-7ec7-44cb-a9f3-bde28a6398eb.png align="center")
    
3. Using `docker logs`
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707805897182/cfbc9923-1482-4a7a-95ca-e8244a73e6f4.png align="center")
    
4. Docker stop and Docker start
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707805922455/050bf52d-e53f-4e6e-a149-1c4303660f97.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707805945273/ea703ed6-cddc-4e26-a8ce-a250f6ac93c0.png align="center")
    
5. docker rm to remove the container
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707805975952/b03f4acb-2c16-45f4-8ab5-0a78167760f5.png align="center")
    

## Conclusion

That wraps up our exploration of Docker Compose and YAML! 🐳✨

In this blog, we've uncovered Docker Compose's prowess in managing multi-container applications, leveraging the simplicity and power of YAML for configuration.

With a deep dive into YAML's components, we've learned how to craft concise and readable configuration files for our Dockerized apps.

Stay tuned for our next blog, where we'll dive even deeper into the world of Docker. Keep learning, keep sharing, and happy containerizing!

Ending with a quote

> Containers are not just about packaging software, they're about packaging ideas.

Happy Learning.