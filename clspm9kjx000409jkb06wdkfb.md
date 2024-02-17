---
title: "Day 22 - Getting Started with Jenkins"
seoTitle: "Introduction to Jenkins"
datePublished: Sat Feb 17 2024 05:06:43 GMT+0000 (Coordinated Universal Time)
cuid: clspm9kjx000409jkb06wdkfb
slug: day-22-getting-started-with-jenkins
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1708142817420/bbf0af13-feb9-4eea-9e09-1c167172ee23.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1708146379733/5672ab7d-ea27-4799-9d15-3ceae7e1ade4.png
tags: docker, aws, kubernetes, devops, jenkins, cicd, 2articles1week, ci-cd, devops-articles, jenkins-devops, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge, jenkins-installation, jenkins-pipeline

---

## Introduction

Hey there, fellow DevOps enthusiasts and eager learners! Today, we're diving into the exciting world of continuous integration and continuous delivery (CI/CD), and we're kicking things off by shining a spotlight on one of the most pivotal tools in the game: Jenkins.

In this blog, we're going to break down Jenkins to its core, demystify the CI/CD workflow, and have an honest chat about the upsides and downsides of integrating a CI/CD tool into your development process. Plus, stick around till the end because we've got a hands-on task lined up for you to really put your newfound knowledge to the test.

So, grab a seat, buckle up, and let's embark on this journey together. Let's get started!

## CI/CD

### What is CI/CD?

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708142761545/81a9efaf-e785-493f-9a88-1f816096c724.png align="center")

CI/CD Continuous Integration and Continuous Deployment, is a process of automating an application deployment process that automatically deploys the application in real time, whenever there are changes made in the application.

This process reduces human intervention, which cuts down errors to bare minimum.

1. **Continuous Integration (CI)**: This practice involves automatically integrating code changes from multiple developers into a shared repository frequently, typically several times a day. Each integration is verified by an automated build process (including tests) to detect integration errors as quickly as possible. CI aims to improve the quality of software, reduce integration issues, and provide rapid feedback to developers.
    
2. **Continuous Deployment (CD)**: This extends CI by automatically deploying code changes to production environments after passing all tests. With CD, the entire process of deploying code, from integration to production, is automated. This automation reduces the risk of human error and accelerates the delivery of new features and updates to end-users.
    

### Pros and Cons of CI/CD

**Pros:**

1. Faster Time to Market
    
2. Higher Quality Software
    
3. Increased Collaboration
    
4. Reduced Risk
    
5. Scalability
    

**Cons:**

1. Initial Setup Complexity
    
2. Resource Intensive
    
3. Overhead for Small Projects
    
4. Dependency on Automation
    
5. Security Concerns
    

### Tools For CI/CD

The List of some of the widely used CI/CD tools are:

1. Jenkins
    
2. GitLab CI/CD
    
3. Azure DevOps
    
4. GitHub Actions
    
5. AWS CodePipeline
    

## Jenkins

![](https://www.hellopz.com/assets/JenkinsLogo.jpg align="center")

Jenkins is the powerhouse of continuous integration and continuous delivery/deployment (CI/CD) automation. Written in Java, this open-source DevOps tool serves as the backbone for implementing seamless CI/CD workflows, known as pipelines.

At its core, Jenkins is all about automation. It provides developers with a versatile platform to build, test, and deploy software efficiently. And because it's open-source, it's accessible to all, fostering collaboration and innovation within development teams.

Operating on Java, Jenkins ensures reliability and scalability in handling diverse automation tasks. Whether it's orchestrating CI processes or facilitating end-to-end automation, Jenkins has got you covered.

One of the key strengths of Jenkins lies in its extensibility through plugins. These plugins act as building blocks, enabling integration with various DevOps stages and tools. Need to integrate Git for version control? There's a plugin for that. How about Maven for project management? Yup, there's a plugin for that too.

Whether it's Amazon EC2, HTML publishing, or any other tool in your toolkit, Jenkins plugins pave the way for seamless integration and automation across your development pipeline.

### How Does Jenkins Work

Here's a Step-by-Step procedure of how Jenkins work:

1. **Setup**: Jenkins is installed on a server and configured via a web interface.
    
2. **Jobs**: In Jenkins, tasks are automated through jobs. A job can represent a build process, a test suite, or any other automation task. Users can create new jobs via the Jenkins web interface or by defining job configurations in Jenkinsfiles (a Groovy-based DSL for defining Jenkins pipeline as code).
    
3. **Triggers**: Jobs are triggered manually or automatically based on events like code commits.
    
4. **Execution**: When a job is triggered, Jenkins allocates resources (like build agents) to run the job. These resources can be on the same server as Jenkins or distributed across multiple machines. Jenkins executes the steps defined in the job configuration, which could involve tasks such as compiling code, running tests, deploying applications, etc.
    
5. **Feedback**: Jenkins provides real-time feedback during job execution. Users monitor job progress, view logs, and receive status updates.
    
6. **Integration**: Jenkins integrates with version control systems and tools through plugins.
    
7. **Extensibility**: Jenkins has a rich ecosystem of plugins that extend its functionality. Users can install plugins to add support for additional version control systems, build tools, testing frameworks, cloud services, and more. Plugins allow Jenkins to be highly customizable and adaptable to different development environments and workflows.
    

### **Installation Guide**

Software requirements:

* Java Should Be installed.
    

**Installation of Java**

Jenkins requires Java to run, yet not all Linux distributions include Java by default. Additionally, not all Java versions are compatible with Jenkins.

There are multiple Java implementations which you can use. OpenJDK is [](https://openjdk.java.net/)the most popular one at the moment, we will use it in this guide.

Update the Debian apt repositories, install OpenJDK 17, and check the installation with the commands:

```bash
sudo apt update
sudo apt install fontconfig openjdk-17-jre
java -version
openjdk version "17.0.8" 2023-07-18
OpenJDK Runtime Environment (build 17.0.8+7-Debian-1deb12u1)
OpenJDK 64-Bit Server VM (build 17.0.8+7-Debian-1deb12u1, mixed mode, sharing)
```

### For Linux:

On Debian and Debian-based distributions like Ubuntu you can install Jenkins through `apt`.

```bash
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```

Copy and Run the commands in the terminal to Install Jenkins.

For Other Operating system, [visit Here](https://www.jenkins.io/doc/book/installing/).

### Hands On Practice

## Tasks:

**1\. What you understood in Jenkin, write a small article in your own words (Don't copy from Internet Directly)**

**2.Create a freestyle pipeline to print "Hello World!!** Hint: Use link for [Article](https://www.geeksforgeeks.org/what-is-jenkins/)

Don't forget to post your progress on Linkedin.

## Conclusion

As we wrap up our discussion on Jenkins and CI/CD, it's clear that this tool is a game-changer in the world of software development. Jenkins doesn't just automate processes; it streamlines collaboration, enhances quality, and speeds up delivery. By breaking down complex setups and offering a plethora of plugins, Jenkins makes it easy for teams to adopt CI/CD practices.

As you embark on your Jenkins journey, remember to keep experimenting, learning, and sharing your experiences. After all, that's what the DevOps community is all about – continuous improvement and collaboration.

Happy coding, and may your pipelines always run smoothly! I hope this blog added some value to your learning. Ending this with a quote

> Everything you can imagine is real. - Pablo Picasso

Happy Learning