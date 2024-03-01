---
title: "Day 35 - Kubernetes ConfigMaps and Secrets"
seoTitle: "Kubernetes Configmaps and Secrets"
datePublished: Fri Mar 01 2024 08:56:34 GMT+0000 (Coordinated Universal Time)
cuid: clt8f78f7000g09l5gtgn9k6n
slug: day-35-kubernetes-configmaps-and-secrets
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1709283270491/ea79fa6b-c1a9-4296-80aa-ec860dcb09ab.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1709283303507/2dba3249-60f2-418c-aacc-f80fda6fece2.png
tags: docker, aws, kubernetes, devops, hashnode, k8s, 2articles1week, hashnodecommunity, technical-writing-1, devops-articles, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge, kubernetes-configmap, devopscommunity

---

## Introduction

Understanding ConfigMaps and Secrets in Kubernetes In the extensive environment of Kubernetes, handling configuration records and sensitive facts is essential for retaining the integrity and protection of your packages. This is in which ConfigMaps and Secrets come into play.

In this blog, we will delve into what ConfigMaps and Secrets are, their significance, and how you may successfully make use of them to your Kubernetes deployments.

## What are ConfigMaps and Secrets?

**ConfigMaps**

ConfigMaps are a Kubernetes resource used to store configuration statistics inside the shape of key-value pairs. They act as a centralized repository for configuration settings that can be used by various components inside your stack.

ConfigMaps are in particular useful for storing environment variables, command-line arguments, configuration documents, and other types of static configuration information.

**Secrets**

On the other hand, Secrets are designed to deal with sensitive data which include passwords, API tokens, and encryption keys securely.

Secrets are saved in an encrypted layout inside Kubernetes and may be hooked up into containers as volumes or exposed as surroundings variables. By leveraging Secrets, you could ensure that sensitive records stays included and inaccessible to unauthorized customers or techniques.

### Analogous Scenario:

To clear the concepts of ConfigMaps and Secrets, we could say we are in charge of managing an advanced spaceship – our Kubernetes cluster.

This spaceship comprises several intricate components (boxes) that require particular information to feature optimally.

\- **ConfigMaps**: Think of ConfigMaps as a highly organized file cabinet within our spaceship.

Each drawer represents a ConfigMap containing important records classified with specific keys. These ConfigMaps keep the configuration settings required by exceptional additives of our spaceship, making sure seamless operation.

\- **Secrets**: Conversely, Secrets functions as a super safe vault onboard our spaceship. Within this vault lies sensitive statistics critical for the project's success – encrypted passwords, access tokens, and other personal facts.

By utilizing Secrets, we protect our spaceship against unauthorized entry to vital facts, retaining the integrity of our task.

### Task 1:

Working with ConfigMaps Now, permit's delve into a realistic demonstration of making and making use of ConfigMaps inside Kubernetes deployments.

### **Step 1:** Creating a ConfigMap

Firstly, we will create a ConfigMap containing our configuration records the usage of both a file or command-line interface.

```bash
kubectl create configmap my-config --from-file=config-file.properties
```

### Step 2: Updating Deployment

Next, we will update our deployment configuration (\`deployment.Yml\`) to consist of the newly created ConfigMap.

```bash
spec:
  template:
    spec:
      containers:
      - name: my-container
        ...
        volumeMounts:
        - name: config-volume
          mountPath: /etc/config
      volumes:
      - name: config-volume
        configMap:
          name: my-config
```

### Step 3: Applying Changes

Apply the updated deployment to your Kubernetes cluster within the particular namespace.

```bash
kubectl apply -f deployment.yml -n <namespace-name>
```

### Step four: Verification

Verify the creation and status of the ConfigMap within your namespace.

```bash
bashCopy codekubectl get configmaps -n <namespace-name>
```

## **Task 2: Managing Secrets**

Similarly, let's explore how to create and manage Secrets within Kubernetes deployments.

### **Step 1: Creating a Secret**

Create a Secret containing sensitive data required by your application.

```bash
bashCopy codekubectl create secret generic my-secret --from-literal=password=supersecretpassword
```

### **Step 2: Updating Deployment**

Update your deployment configuration (`deployment.yml`) to include the newly created Secret.

```bash
spec:
  template:
    spec:
      containers:
      - name: my-container
        ...
        volumeMounts:
        - name: secret-volume
          mountPath: /etc/secret
      volumes:
      - name: secret-volume
        secret:
          secretName: my-secret
```

### **Step 3: Applying Changes**

Apply the updated deployment to your Kubernetes cluster within the specified namespace.

```bash
kubectl apply -f deployment.yml -n <namespace-name>
```

### **Step 4: Verification**

Verify the creation and status of the Secret within your namespace.

```bash
kubectl get secrets -n <namespace-name>
```

## Conclusion

ConfigMaps and Secrets are essential gear within the Kubernetes arsenal, allowing efficient control of configuration facts and sensitive statistics inside your deployments.

By leveraging these sources successfully, you can streamline your application's configuration process whilst ensuring the safety and integrity of your Kubernetes workloads.

So, whether you're piloting a spaceship through the cosmos or orchestrating containerized packages in Kubernetes, ConfigMaps and Secrets are your depended on allies in navigating the complexities of modern infrastructure. 🚀

> The question isn't who is going to let me; it's who is going to stop me.

Happy Learning.