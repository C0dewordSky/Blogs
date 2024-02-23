---
title: "Day 28 - Jenkins Agents"
seoTitle: "Jenkins Agents"
datePublished: Fri Feb 23 2024 08:58:55 GMT+0000 (Coordinated Universal Time)
cuid: clsyf7aiw00000ajuhommgu1q
slug: day-28-jenkins-agents
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1708678504222/8cbecf08-2db2-4322-be92-38f16526f730.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1708678717993/f0b654e0-7514-4ca2-9632-9a701c5cf6b1.png
tags: cloud, docker, aws, developer, cloud-computing, devops, hashnode, aws-lambda, jenkins, 2articles1week, technical-writing-1, devops-articles, devops-journey, trainwithshubham, devopscommunity

---

## Introduction

Welcome DevOps enthusiasts. In this blog, we aim to demystify the concept of Jenkins agents and offer a step-by-step walkthrough to set up and leverage them effectively inside your CI/CD pipelines.

Whether you're a seasoned DevOps engineer seeking to optimize your workflow or a newcomer keen to harness the power of Jenkins, this article will equip you with the expertise and gear needed to streamline your Jenkins workflows using agents.

## Understanding Jenkins Agents

### Jenkins Master (Server)

The Jenkins master, analogous to a control tower, holds critical configurations and orchestrates workflow pipelines. It schedules and monitors jobs, providing a centralized hub for managing continuous integration and delivery processes.

In simple words, think of it as your BOSS, who assigns and orchestrate your tasks, provides resources, data etc. to streamline the workflow.

### Jenkins Agent

Conversely, a Jenkins agent acts as an execution environment for jobs described in pipelines. Agents can be machines or containers connected to the Jenkins master, capable of executing tasks delegated by the master. Each agent is assigned a unique label for identification.

In the execution flow, when a task is triggered from the master, the actual execution takes place on the designated agent node. This distributed architecture enables scalable and efficient job execution, particularly as project requirements evolve.

## Pre-requirements

Before delving into setting up Jenkins agents, ensure the following prerequisites are met:

### Install Java

```bash
sudo apt update
sudo apt install default-jdk
```

### Install Docker

```bash
sudo apt update
sudo apt install docker.io
sudo systemctl start docker
sudo systemctl enable docker
```

### SSH Configuration

Generate SSH key pair on Jenkins Master:

```bash
ssh-keygen -t rsa 
```

Copy public key to Jenkins Agent:

```bash
ssh-copy-id jenkins_agent_username@agent_ip_address
```

## Task-01: Setting Up Jenkins Agent Node

To create a Jenkins agent node and establish connectivity with the master, follow these steps:

1. **Create AWS EC2 Instance**: Provision a new AWS EC2 instance and configure it to connect with the Jenkins master.
    
    * Ensure correct networking configurations to facilitate communication between the master and agent nodes.
        
2. **SSH Configuration**: Set up SSH connectivity between the master and agent nodes by exchanging public-private key pairs.
    
    * Verify SSH connectivity to ensure seamless communication between the nodes.
        
3. **Node Setup on Jenkins Master**: Add the newly provisioned EC2 instance as a node on the Jenkins master.
    
    * Provide relevant configurations including node name, labels, and connection info.
        
4. **Verify Node Status**: Confirm the successful addition of the agent node under the "Nodes" section in the Jenkins dashboard.
    
    * Ensure proper connectivity and readiness of the agent node for job execution.
        

## Task-02: Running Jobs at the New Agent

Once the agent node is set up, proceed to execute previous jobs on the new agent using the following steps:

1. **Job Configuration**: Configure the jobs built on Day 26 and Day 27 to utilize the newly added agent node.
    
    * Specify appropriate labels to ensure the master triggers builds on the designated agent.
        
2. **Job Execution**: Trigger the execution of jobs, allowing the master to delegate tasks to the connected agent node.
    
    * Monitor job execution status to ensure successful completion on the agent node.
        

Jenkins facilitates seamless distribution of workload, optimizing resource utilization, and enhances workflow performance.

## Conclusion

In conclusion, Jenkins agents play a pivotal role in streamlining continuous integration and delivery pipelines, enabling scalable and efficient job execution. By understanding the underlying principles and following the outlined steps, teams can harness the full potential of Jenkins agents to drive automation and accelerate software delivery processes.

Ending this with a quote

> Every accomplishment starts with the decision to try.

Happy Learning.