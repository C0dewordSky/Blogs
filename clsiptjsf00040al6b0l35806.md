---
title: "Day 17 - Dockerfile and Docker Project"
seoTitle: "Dockerfile and Docker Project"
datePublished: Mon Feb 12 2024 09:11:51 GMT+0000 (Coordinated Universal Time)
cuid: clsiptjsf00040al6b0l35806
slug: day-17-dockerfile-and-docker-project
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707719476724/863592a4-f4ea-4370-b4cd-c291d792d7b5.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1707729057564/515e6062-aa6b-4df3-b877-2f9af174aabf.png
tags: blogging, docker, aws, kubernetes, devops, hashnode, dockerfile, 2articles1week, technical-writing-1, devops-articles, devops-journey, trainwithshubham, devopscommunity

---

## Introduction

Welcome DevOps enthusiasts and learners. In today's blog we're gonna delve deep into Docker, understanding the process of packaging a software and creating its Image. The most crucial tool for that is a Dockerfile. We'll understand what it is, its components and how to write it.

Along with that, our tradition to solve hands on problem by the end will remain the same and we're gonna end this blog with an interactive hands on practice session. So without any further ado, let's jump into learning.

### What is an image?

An image is the packaged, light-weight version of a application, containing all the essential packages and dependencies, that can run inside a container.

It gives us the freedom to deploy and manage applications across different platforms and environments, makes it scalable, easily available and easy to transport meaning they can be easily transferred between different systems or shared with others, making them an efficient way to distribute software.

## Dockerfile

To Create images in docker, Dockerfile comes handy. Its the method of writing a script to create images based on the configuration mentioned inside the script.

It outlines the steps needed to create the image, including specifying the base image, copying files into the image, setting environment variables, and running commands.

The Dockerfile provides a declarative way to define the configuration of the image, making it easy to understand and reproduce the image-building process.

### Writing a Dockerfile:

Before we head on to see how a dockerfile is written, let's Understand some commands used inside a Dockerfile.

Here's the information presented in a table format:

| Command | Purpose |
| --- | --- |
| FROM | To specify the base image which we want to use. |
| WORKDIR | To define the working directory for any commands in the Dockerfile. |
| RUN | To install a package or any application. |
| COPY | To copy over files or directories from a specific location. |
| ADD | Same as COPY, but we can also use a URL instead of a local file/directory and extract a tar file from the source directly into the destination. |
| ENTRYPOINT | Command that will always be executed when the container starts. If not specified, the default is /bin/sh -c. |
| CMD | To define a default command to run when your container starts. |
| EXPOSE | To define which port through which to access your container application. |
| LABEL | To add metadata to the image. |

**DOCKERFILE SYNTAX :**

```bash
FROM <base_image>

WORKDIR /app

COPY . .

RUN [command]

CMD ["",""]
```

DOCKERFILE Example:

In this example we are creating an image of an imaginary python app

```bash
FROM ubuntu:latest

WORKDIR ./app

COPY . .

RUN apt-get -y update  && apt-get install -y python

CMD ["python","app.py"]  
```

### Understanding the Dockerfile:

The Dockerfile is explained line by line below:

```bash
FROM ubuntu:latest
```

*#* ***Using official ubuntu image as a parent image***

1. Docker files start from a ‘parent’ image. The parent image is added through the `FROM` keyword. Your image builds upon the parent image.
    
2. The base image typically contains a minimal operating system environment (such as Alpine Linux, Ubuntu, CentOS, etc.) along with any necessary dependencies or packages required for your application to run..
    

*#* ***Setting the working directory to /app***

```bash
WORKDIR /app 
```

1. You then set the working directory in your container with `WORKDIR`. `WORKDIR /app` sets the current directory to `/app` when the container starts running.
    

*#* ***Copy the current directory contents into the container at /app***

```bash
COPY . .
```

1. So far, we have the Ubuntu OS in our environment with the current directory set to `/app`. Now we want to transfer our own files into the container from the outside. We do this using `COPY . .` where the `COPY` command copies all the files from our current directory (the one which contains the Dockerfile) into the set current directory i.e. `/app`.
    
2. Our container will now contain the Ubuntu OS and the files from our local directory with the working directory set to `./app`. That’s it! The container will only have the things you specify it to have.
    

*#* ***Getting the updates for Ubuntu and installing python into our environment***

```bash
RUN apt-get -y update  && apt-get install -y python
```

1. The `RUN` command executes when we build the image and any additional dependencies or packages are usually installed using the `RUN` command. We assume that we have the OS image we specified and build other packages on top of it.
    

*#* ***Run app.py when the container launches***

```bash
CMD ["python", "app.py"]
```

1. The `CMD` specifies the command which is executed when we start the container.
    

## Commands

To build a Docker image, you typically use the `docker build` command followed by the path to the directory containing your Dockerfile. Here are the basic steps along with the command syntax:

1. Navigate to the directory containing your Dockerfile and any other necessary files for your Docker image.
    
2. Use the `docker build` command to build the image. The basic syntax is:
    
    ```bash
    docker build [option] [path] 
    ```
    

* `[OPTIONS]` are additional options you can specify for the build process. Some common options include:
    
    * `-t` or `--tag`: Tag the image with a name and optionally a tag in the `name:tag` format.
        
    * `-f` or `--file`: Specify the name of the Dockerfile if it's not named `Dockerfile`.
        
    * `--build-arg`: Set build-time variables that can be used in the Dockerfile.
        
    * `--no-cache`: Build the image without using any cache from previous builds.
        
    * `--rm`: Remove intermediate containers after a successful build.
        
* `PATH` is the path to the directory containing the Dockerfile and any other files required for the build.
    

**EXAMPLE**:  
Here's an example command to build a Docker image named `myapp` with the tag `latest` from the current directory:

```bash
Copy codedocker build -t myapp:latest .
```

This command assumes that the Dockerfile is named `Dockerfile` and is located in the current directory. If your Dockerfile has a different name or is located in a different directory, you can use the `-f` option to specify the Dockerfile's path:

```bash
bashCopy codedocker build -t myapp:latest -f /path/to/Dockerfile .
```

NOTE: DO NOT forget the " . " at the end of the command. This specifies the current directory to build the image.

Read more about Dockerfile, [Here](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#:~:text=What%20is%20a%20Dockerfile%3F,to%20build%20a%20given%20image.).

## Pushing Image to Docker Hub

STEP 1 : Create an Account on Docker Hub and log in via cli.

```bash
docker login 
```

STEP 2 : **Tag the Image**: Before pushing the image, you need to tag it with your Docker Hub username and the repository name.

```bash
docker tag local-image:tag username/repository:tag
```

STEP 3 : **Push the Image**: Once the image is tagged, you can push it to Docker Hub using the `docker push` command.

```bash
docker push username/repository:tag
```

## Practice

Tasks:

* Create a Dockerfile for a simple web application (e.g. a Node.js or Python app)
    
* Build the image using the Dockerfile and run the container
    
* Verify that the application is working as expected by accessing it in a web browser
    
* Push the image to a public or private repository (e.g. Docker Hub )
    

## Solution

Use This repo for the sample application Link: [https://github.com/shreys7/django-todo](https://github.com/shreys7/django-todo)

1. Creating a Dockerfile
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707727226349/5f7e759e-e3ba-44a8-ae6e-5c5e7a6bb60b.png align="center")
    
    1. Docker Image Built
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707727273352/642b413a-8c12-4874-a50e-9eab14bc24ee.png align="center")
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707727283145/4a73a7cb-d081-4eda-aaac-1d1986879550.png align="center")
        
        1. Running
            
            ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707727414945/c938e502-d0ba-486b-a73d-5c74a41c4f87.png align="center")
            
            ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707727451484/ac823def-bd0d-44ec-94ec-61f33057bf79.png align="center")
            
            1. Use the "Push" command and Upload it on Dockerhub and it will show you the repository as follows:
                
                ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707728655154/30c87a79-941d-40b3-b68e-7c8052107921.png align="center")
                

## Conclusion

In this session, we delved into the realm of images and explored the methodologies to craft them using Dockerfile. We meticulously examined the pivotal commands, culminating in a hands-on practice session. With that, we draw the curtains on this blog. Until next time, may this journey have enriched your learning experience. Farewell, and see you in the next installment.

Ending with a quote

> Learning is a treasure that follows its owner everywhere. - Chinese Proverb

Happy learning

**<mark>NOTE: There will be a separate blog on the project mentioned above so stay tuned.</mark>**