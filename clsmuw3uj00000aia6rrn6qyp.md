---
title: "Day 20 - Docker Cheat-Sheet"
seoTitle: "Docker Cheat-Sheet"
datePublished: Thu Feb 15 2024 06:44:53 GMT+0000 (Coordinated Universal Time)
cuid: clsmuw3uj00000aia6rrn6qyp
slug: day-20-docker-cheat-sheet
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707974716339/af09541e-73c9-4436-966e-38e989a7747e.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1707979456417/89760252-15b4-44ef-8dbb-6f12b0785648.png
tags: cloud, linux, docker, aws, kubernetes, devops, cheatsheet, 2articles1week, technical-writing-1, devops-articles, devops-journey, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge, devopscommunity

---

## Introduction

Welcome DevOps enthusiasts and learners. In this blog we're gonna get our hands dirty and sum up all the concepts that we have learnt in the past few days about docker. We are going to create our very own cheat sheet for our future revisions and references.

From Day 16 to Day 19, we're gonna sum up every concepts and create a comprehensive cheat-sheet for ourselves. So without delaying, let's just begin.

## Commands

Here's the cheat-sheet of Docker commands according to the tasks they perform:

1. **To pull an Image from Docker Hub:**
    
    ```bash
    docker pull <image_name>:version
    ```
    
2. **To run a container:**
    
    ```bash
    docker run <image_name>
    ```
    
3. **Flags for running a container:**
    
    ```bash
    -d: to run in background
    ```
    
4. **To inspect a container:**
    
    ```bash
    docker inspect <container_name>
    ```
    
5. **List of Running Containers:**
    
    ```bash
    docker ps
    ```
    
6. **List all the containers (Running or stopped):**
    
    ```bash
    docker ps -a
    ```
    
7. **List of images on the system:**
    
    ```bash
    docker images
    ```
    
8. **Docker Port Mapping:**
    
    ```bash
    docker run -p host_port:container_port <image_name>
    ```
    
9. **Map a volume:**
    
    ```bash
    docker run -v HOSTDIR:TARGETDIR <image_name>
    ```
    
10. **To assign a name to the container while running:**
    
    ```bash
    docker run --name Name <Image_name>
    ```
    
11. **To stop a container:**
    
    ```bash
    docker stop <container_name_or_id>
    ```
    
12. **To start a stopped container:**
    
    ```bash
    docker start <container_name_or_id>
    ```
    
13. **To kill a container:**
    
    ```bash
    docker kill <container_name_or_id>
    ```
    
14. **To remove a container:**
    
    ```bash
    docker rm <container_name_or_id>
    ```
    
15. **Delete a running container:**
    
    ```bash
    docker rm -f <container_name_or_id>
    ```
    
16. **Copy files from container to host:**
    
    ```bash
    docker cp <container_name>:<file_name> <file_name>
    ```
    
17. **Copy files from host to container:**
    
    ```bash
    docker cp <file_name> <container_name>:<file_source>
    ```
    
18. **Run a command inside a running container:**
    
    ```bash
    docker exec -it <container_name> <name_of_shell>
    ```
    
19. **Create an image out of a container:**
    
    ```bash
    docker commit <container_name_or_id>
    ```
    
20. **To delete an image:**
    
    ```bash
    docker rmi <image_name>
    ```
    
21. **To delete all images:**
    
    ```bash
    docker image prune -a
    ```
    
22. **To remove unused resources (container, Images, etc.):**
    
    ```bash
    docker system prune
    ```
    
23. **Build an image from Dockerfile:**
    
    ```bash
    docker build DOCKERFILE
    ```
    
24. **Build and tag the image at the same time:**
    
    ```bash
    docker build -t <Name> <DockerFile> .
    ```
    
25. **Tag an image:**
    
    ```bash
    docker tag <image_id_or_name> <new_tag>
    ```
    
26. **To connect with your Docker Hub account:**
    
    ```bash
    docker login <registry_url>/<repository_name>:<tag>
    ```
    
27. **Push an image to Docker Hub:**
    
    ```bash
    docker push <registry_url>/<repository_name>:<tag>
    ```
    
28. **See Logs of container:**
    
    ```bash
    docker logs <Container_name_or_id>
    ```
    
29. **See Modified files in a container:**
    
    ```bash
    docker diff <Container_name>
    ```
    
30. **See the stats of the running container:**
    
    ```bash
    docker stats
    ```
    
31. **Delete Stopped containers:**
    
    ```bash
    docker containers prune
    ```
    
32. **Rename a container:**
    
    ```bash
    docker rename <Old_name> <New_Name>
    ```
    
33. **Save an image to a tar file:**
    
    ```bash
    docker save <Image> > FILE.tar
    ```
    
34. **Load an image from a tar file:**
    
    ```bash
    docker load -i FILE.tar
    ```
    

## Conclusion

In this cheat sheet, we covered the extensive set of Docker commands needed to manage containers, images, volumes, and more. Whether you're a beginner Docker installer or an experienced user looking to simplify your workflow, these commands provide intuitive tutorials for tasks ranging from running containers to images managing types to connectivity and troubleshooting.

By getting these commands right, you can effectively deploy, monitor, and maintain them, empowering you to use the full power of Docker in your development and deployment planning. With the knowledge in this cheat sheet, you're ready to enter the world of containerization with confidence.

I hope this blog added some Value to your learning. Do curate and share your own chat-sheet on LinkedIn and don't forget to tag me.

Ending this with a quote

> Every great developer you know got there by solving problems they were unqualified to solve until they actually did it. - Patrick McKenzie

Happy Learning.