---
title: "Day 40 - Automating EC2 Deployments with Launch Templates"
seoTitle: "Day 40 - Automating EC2 Deployments with Launch Templates"
datePublished: Fri Mar 29 2024 08:43:03 GMT+0000 (Coordinated Universal Time)
cuid: clucf1orh000708jv2f6e5yeb
slug: day-40-automating-ec2-deployments-with-launch-templates
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/rymh7EZPqRs/upload/a8c558f27269af926e6db968e45274b6.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1711701710632/d5de542d-3287-4361-bc9d-fb410af7cdbf.png
tags: ec2, docker, aws, kubernetes, containers, technical-writing-1, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge

---

## Introduction

This blog post explores automation in Amazon EC2, focusing on Launch Templates and their role in streamlining instance deployments. We'll delve into core concepts like AMIs, instance types, and Launch Templates, before diving into practical examples of creating a template and launching instances.

### Introduction to EC2 Automation

Amazon EC2 offers a robust cloud computing platform for deploying and managing virtual servers. While the web console provides a user-friendly interface, repetitive tasks can become time-consuming. Automation is key to efficient EC2 management.

### Understanding Launch Templates

A Launch Template acts as a blueprint for launching EC2 instances. It stores configuration details like AMI (Amazon Machine Image), instance type, security groups, and user data scripts. This eliminates the need to manually specify these parameters every time you launch an instance.

**Benefits of Launch Templates:**

* **Consistency:** Ensures all instances launched from the template have the same configuration.
    
* **Versioning:** Create and manage multiple versions of a template for different configurations.
    
* **Reusability:** Easily launch new instances with pre-defined configurations.
    

### Key Concepts: AMIs and Instance Types

* **AMI (Amazon Machine Image):** An AMI is a pre-configured software bundle containing the operating system, applications, and configurations needed to launch an instance.
    
* **Instance Types:** EC2 offers a wide range of instance types optimized for various workloads. Each type provides a specific combination of CPU, memory, storage, and networking capabilities.
    

**Choosing the Right Configuration:**

For this example, we'll use the Amazon Linux 2 AMI and the t2.micro instance type. <mark>The t2.micro is a cost-effective option for low-to-medium CPU workloads.</mark>

**Installing Jenkins and Docker:**

We'll leverage user data scripts to automate the installation of Jenkins and Docker on launched instances. You can find a sample script for Day 39 User Data.

### Task 1: Creating a Launch Template

1. **Navigate to the EC2 Launch Templates console.**
    
2. **Click "Create Launch Template".**
    
3. **Provide a name and description for your template.**
    
4. **Under "Image ID", select the Amazon Linux 2 AMI.**
    
5. **Under "Instance Type", choose the t2.micro instance type.**
    
6. **Configure security groups to allow inbound traffic for SSH and necessary ports for Jenkins and Docker.**
    
7. **Paste your user data script containing the installation commands for Jenkins and Docker.**
    
    ```bash
    #!/bin/bash
    # User Data Script for Jenkins and Docker setup
    sudo yum update -y
    sudo yum install -y java-1.8.0-openjdk-devel
    sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
    sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
    sudo yum install -y jenkins
    sudo systemctl start jenkins
    sudo systemctl enable jenkins
    sudo amazon-linux-extras install docker
    sudo systemctl start docker
    sudo systemctl enable docker
    ```
    
8. **Review and create the Launch Template.**
    

**<mark>Note: The EC2 console doesn't offer a direct option to specify the number of instances to launch during template creation.</mark>**

### Launching Instances from the Template

1. **Navigate to the EC2 "Run Instances" console.**
    
2. **Under "Launch source", choose "Launch template".**
    
3. **Select the Launch Template you created.**
    
4. **Configure additional options like network settings and IAM roles (if needed).**
    
5. **Specify the number of instances you want to launch (e.g., 3).**
    
6. **Review and launch the instances.**
    

### Auto Scaling Groups

For automated scaling based on demand, create an Auto Scaling group. This group manages a pool of EC2 instances based on predefined scaling policies. The Launch Template you created can be used as the launch configuration for the Auto Scaling group.

### **Creating an Auto-Scaling Group**

To create an auto-scaling group, follow these steps:

1. Navigate to the AWS EC2 console and select "Auto Scaling Groups."
    
2. Click on "Create Auto Scaling Group" and configure the group settings, including instance configuration, scaling policies, and desired capacity.
    
3. Define scaling policies based on metrics such as CPU utilization or request count to scale instances in or out dynamically.
    

**NOTE:** <mark>Auto-scaling groups automatically adjust the number of EC2 instances based on workload patterns, optimizing performance and cost-efficiency.</mark>

## Conclusion

This blog post provides a foundational understanding of automating EC2 deployments with Launch Templates. With practice, you can leverage these tools to create efficient and scalable infrastructure on AWS.

> The future belongs to those who believe in the beauty of their dreams.

Happy Learning.