---
title: "Day - 32 : Kubernetes Deployment"
seoTitle: "Kubernetes Deployment"
datePublished: Tue Feb 27 2024 09:53:53 GMT+0000 (Coordinated Universal Time)
cuid: clt46xdyx000d08ju3av2g4w7
slug: day-32-kubernetes-deployment
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1709027500119/ea8fbd11-21a7-4fa5-91da-f8390fdd7244.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1709027607082/f276fd71-f4b7-4ca5-b658-720203e3279b.png
tags: docker, aws, kubernetes, devops, hashnode, containers, containerization, technical-writing-1, devops-articles, devops-journey, 90daysofdevops, container-orchestration, trainwithshubham, 90daysofdevops-chanllenge, devopscommunity

---

## Introduction

Welcome DevOps enthusiasts and learners. In Kubernetes (K8s), a Deployment plays a crucial role in managing and scaling applications. Whether you're an experienced DevOps engineer or a beginner exploring container orchestration, understanding Deployments is essential for effectively managing Kubernetes clusters.

**What is Deployment in K8s?**

At its core, a Deployment in Kubernetes provides a declarative approach to defining and managing the lifecycle of Pods and ReplicaSets. But what does that mean practically?

Imagine you have an application, let's say a "todo-app," that you want to run on Kubernetes. Instead of manually creating and managing Pods and ReplicaSets, which becomes cumbersome as your application scales or requires updates, Deployments offer a solution.

Using Deployments, you can describe the desired state of your application, including the number of replicas, container image, and other configurations necessary for your app to function correctly.

**Key Features of Deployments**

1. **Desired State Management:**
    
    * Deployments enable specifying the desired state of your application, including the number of replicas and their characteristics.
        
2. **Rolling Updates:**
    
    * Facilitates rolling updates, ensuring the gradual rollout of the new version while maintaining availability.
        
3. **Rollback Capabilities:**
    
    * Provides rollback capabilities, allowing you to revert to a previous version quickly and seamlessly if an update goes wrong.
        
4. **Auto-Healing:**
    
    * Built-in auto-healing capabilities replace unhealthy Pods automatically, ensuring application availability and resilience.
        
5. **Auto-Scaling:**
    
    * Allows defining metrics such as CPU or memory usage thresholds for auto-scaling the number of replicas based on those metrics.
        

**Task: Deploying a Sample todo-app with Auto-Healing and Auto-Scaling**

**Task-1: Create Deployment File**

1. **Create Deployment File (Blueprint):**
    
    * Start by creating a `deployment.yaml` file containing specifications for your Deployment, including container image, replicas, and other configurations needed.
        
    
    ```yaml
    # deployment.yaml
    
    apiVersion: apps/v1
    type: Deployment
    metadata:
      name: todo-app
    spec:
      replicas: 3
      selector:
        matchLabels:
          app: todo
      template:
        metadata:
          labels:
            app: todo
        spec:
          containers:
          - name: todo-app
            image: your-todo-app-image:latest
            ports:
            - containerPort: 8080
    ```
    
    * Explanation of the `deployment.yaml` contents:
        
        * `apiVersion`: Specifies the API version used (`apps/v1`).
            
        * `type`: Defines the type of Kubernetes resource (Deployment).
            
        * `metadata`: Contains metadata about the Deployment, such as its name.
            
        * `spec`: Specifies the desired state of the Deployment.
            
            * `replicas`: Defines the desired number of Pod replicas (3 in this case).
                
            * `selector`: Identifies which Pods the Deployment manages using labels.
                
                * `matchLabels`: Specifies the labels Pods must have to be managed by the Deployment.
                    
            * `template`: Defines the Pod template used by the Deployment to create new Pods.
                
                * `metadata`: Contains labels applied to Pods created from this template.
                    
                * `spec`: Specifies the Pod's specification.
                    
                    * `containers`: Specifies the containers to run in the Pods.
                        
                        * `name`: Specifies the container's name.
                            
                        * `image`: Specifies the container image to use.
                            
                        * `ports`: Specifies the ports to expose in the container.
                            
2. **Apply Deployment to Kubernetes:**
    
    * Once the `deployment.yaml` file is created, apply it to your Kubernetes cluster using the following command:
        
    
    ```bash
    kubectl apply -f deployment.yaml
    ```
    
    * This command instructs Kubernetes to create the Deployment based on the specifications provided in the YAML file.
        

**Conclusion**

This blog covered the basics of Deployment in Kubernetes. Since Deployments are a fundamental component of Kubernetes which enables efficient management, scaling, and updating of applications. Leveraging features such as auto-recovery and auto-scaling ensures that your applications remain resilient, available, and responsive to changing demands.

We also deployed a sample todo-app using Kubernetes Deployment, laying the groundwork for further exploration and experimentation with container orchestration. So, go ahead, give it a try, and let your resume shine with yet another exciting project in your repertoire!

> The greatest glory in living lies not in never falling, but in rising every time we fall. -Nelson Mandela

Happy Learning.