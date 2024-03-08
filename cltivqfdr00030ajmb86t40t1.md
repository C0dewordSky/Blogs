---
title: "Day 39 - AWS and IAM Basics"
seoTitle: "AWS and IAM Basics"
datePublished: Fri Mar 08 2024 16:37:06 GMT+0000 (Coordinated Universal Time)
cuid: cltivqfdr00030ajmb86t40t1
slug: day-39-aws-and-iam-basics
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1709915725443/26780282-2275-4413-a490-f60395f8ac43.webp
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1709915805666/400951a0-1def-4377-8b71-db1e73c602f5.png
tags: cloud, docker, aws, kubernetes, developer, cloud-computing, devops, hashnode, aws-lambda, iam, 2articles1week, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge, 2024

---

## Introduction

In the vast landscape of cloud computing, Amazon Web Services (AWS) stands tall as one of the leading cloud service providers, offering a plethora of services to cater to various business needs. Whether you're a student diving into the world of cloud computing or a seasoned cloud enthusiast, AWS provides an array of resources, including a free tier, to facilitate hands-on learning and experimentation.

## Pros of Using AWS

### AWS Free Tier

AWS understands the importance of practical learning, especially for students and cloud enthusiasts eager to hone their skills. With the AWS Free Tier, users can embark on their cloud journey without worrying about costs. By creating a free account, users gain access to a plethora of AWS services, allowing them to delve deeper into cloud computing concepts through hands-on experience.

## User Data

When launching an instance in Amazon Elastic Compute Cloud (EC2), users can pass their data. This feature enables users to automate common configuration tasks and execute scripts post-instance launch.

User data in EC2 can be passed in two primary formats: shell scripts and cloud-init directives.

Users can conveniently pass user data through various methods, including plain text input, file uploads, or base64-encoded text for API calls.

This functionality significantly streamlines the process of instance provisioning, saving time and manual effort. Whether it's installing applications like Apache, Docker, or Jenkins, leveraging user data simplifies the setup process, ensuring swift deployment of instances tailored to specific requirements.

## Understanding AWS Identity and Access Management (IAM)

AWS Identity and Access Management (IAM) serves as a cornerstone in AWS's security framework, empowering users to securely manage access to AWS resources. IAM facilitates centralized management of permissions, dictating which AWS resources users can access. By delineating authentication and authorization mechanisms, IAM ensures that only authorized entities can utilize AWS resources.

### IAM Roles

IAM Roles play a crucial role in IAM's architecture, providing microscopic control over resource access. To delve deeper into IAM, let's unravel the concepts of IAM Users, Groups, and Roles:

* **IAM Users**: IAM Users represent individual entities within an AWS environment. Each user is associated with a unique set of credentials, encompassing a username and password or access keys. IAM Users authenticate themselves to access AWS resources, subject to permissions granted by IAM policies.
    
* **IAM Groups**: IAM Groups facilitate the management of multiple IAM Users by organizing them into logical units. By assigning permissions to groups rather than individual users, administrators can streamline access management, ensuring consistency and scalability across user entities.
    
* **IAM Roles**: IAM Roles embody a flexible mechanism for granting temporary access to AWS resources. Unlike IAM Users, which represent permanent entities, IAM Roles are temporary and assumable. Roles are often utilized in scenarios requiring cross-account access, federated access, or resource delegation, offering a secure and auditable approach to resource provisioning.
    

## Practical Tasks: Task 1 and Task 2

### Task 1: Launching an EC2 Instance with Jenkins

In Task 1, we aim to launch an EC2 instance pre-configured with Jenkins, a popular automation server. By leveraging user data, we streamline the installation process, ensuring Jenkins is readily accessible upon instance launch. Following the successful launch, we validate the task completion by accessing the Jenkins page via the instance's IP address.

### Task 2: Exploring IAM Roles and Creating Custom Roles

Task 2 delves into the realm of IAM Roles, offering insights into their significance within AWS's security paradigm. We elucidate the concepts of IAM Users, Groups, and Roles, elucidating their respective roles in access management. Additionally, we embark on the practical aspect by creating three custom IAM Roles: DevOps-User, Test-User, and Admin, showcasing the versatility and granularity of IAM's access control mechanisms.

## Conclusion

By unraveling the intricacies of AWS services like EC2 and IAM, users can unlock a world of possibilities in cloud computing. With practical tasks and conceptual insights, this guide serves as a stepping stone for individuals venturing into the realm of AWS, empowering them to navigate the cloud landscape with confidence and proficiency.

I hope this short blog added some value to your learnings.

> When you have a dream, you've got to grab it and never let go.  
> — **Carol Burnett**

Happy Learning.