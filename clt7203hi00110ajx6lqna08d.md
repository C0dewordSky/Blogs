---
title: "Day 34 - Kubernetes Services"
seoTitle: "Kubernetes Services"
datePublished: Thu Feb 29 2024 09:59:20 GMT+0000 (Coordinated Universal Time)
cuid: clt7203hi00110ajx6lqna08d
slug: day-34-kubernetes-services
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1709200672280/7017efdb-2dac-4e08-a84c-0d1137a7faeb.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1709200742754/94f985c3-77ff-4d3f-a881-04cc68b9d130.png
tags: docker, aws, kubernetes, devops, hashnode, 2articles1week, devops-articles, kubernetes-architecture, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge, devopscommunity, kubeweekchallenge

---

## Introduction

Welcome DevOps enthusiasts and Learners. In Kubernetes (K8s), one of the fundamental concepts that channels networking within the cluster is the concept of Services.

They play a pivotal role in abstracting away the complexities of Pod IP addresses and providing stable network identities to Pods. In this blog post, we will delve into what Services are, their types, and how they facilitate seamless communication within a Kubernetes cluster.

### Understanding Kubernetes Services

Services, in the context of Kubernetes, are objects designed to provide a stable endpoint for accessing a set of Pods.

They act as an intermediary layer that decouples the consumers of a service from the underlying implementation details of the Pods. This abstraction ensures that regardless of the dynamic nature of Pods, the Service remains stable and accessible.

### Types of Kubernetes Services

Kubernetes offers several types of Services to cater to different networking requirements within a cluster. Let's explore each type briefly:

1. **ClusterIP Service**: This type of Service exposes the Pods internally within the cluster. It assigns a cluster-internal IP address to the Service, which remains stable regardless of the underlying Pods' IP addresses. ClusterIP Services are ideal for inter-Pod communication <mark>within the cluster.</mark>
    
2. **NodePort Service**: NodePort Services expose a Service on a static port on each Node in the cluster. <mark>This enables external clients to access the Service using the Node's IP address and the allocated static port.</mark> While NodePort Services are simple to set up, they might not be suitable for production environments due to security and scalability concerns.
    
3. **LoadBalancer Service**: LoadBalancer Services are used to expose a Service to the external world. They provision an external load balancer (in cloud environments) that distributes traffic to the Pods behind the Service.
    
    <mark>LoadBalancer Services are suitable for applications that need to be accessible from outside the cluster.</mark>
    

### **Practical implementation of Kubernetes Services:**

### **Task 1:**

**Creating a Service for the todo-app Deployment**

In this task, we will create a Service definition for the todo-app Deployment and apply it to our Kubernetes cluster using the `kubectl apply -f service.yml -n <namespace-name>` command. This will provide stable network identity to our todo-app Pods.

```bash
apiVersion: v1
kind: Service
metadata:
  name: todo-service
  labels:
   app: todo-app
spec:
  selector:
    app: todo-app
  ports:
    - protocol: TCP
      port: 80
      targetPort: 8000
```

### **Task 2:**

Creating a ClusterIP Service for accessing the todo-app from within the cluster In this task, we will create a ClusterIP Service definition for the todo-app Deployment. This will enable other Pods within the cluster to access the todo-app using the Service's cluster-internal IP address.

```bash
apiVersion: v1
kind: Service
metadata:
  name: todo-service
  labels:
   app: todo-app
spec:
  type: ClusterIP
  selector:
    app: todo-app
  ports:
    - protocol: TCP
      port: 80
      targetPort: 8000
```

### **Task 3:**

Creating a LoadBalancer Service for accessing the todo-app from outside the cluster In this final task, we will create a LoadBalancer Service definition for the todo-app Deployment. By applying this Service definition, we will make the todo-app accessible from outside the cluster, allowing external clients to interact with it.

```bash
apiVersion: v1
kind: Service
metadata:
  name: todo-load-balancer
  labels:
    app: todo
spec:
  type: LoadBalancer
  selector:
    app: todo
  ports:
    - protocol: TCP
      port: 80
      targetPort: 8000
```

### **Conclusion**

Kubernetes Services serve as a vital component in facilitating seamless communication within a Kubernetes cluster. By removing away the complexities of networking, Services ensure that applications running on Pods remain accessible and scalable.

Understanding the different types of Services and their use cases empowers DevOps engineers to design robust networking solutions tailored to their application's requirements. With practical examples outlined in this blog post, deploying Services in Kubernetes becomes more approachable and comprehensible for developers and operators alike.

> It takes courage to grow up and become who you really are.

Happy Learning.