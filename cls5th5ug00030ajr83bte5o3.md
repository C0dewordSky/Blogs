---
title: "Day 8 - Basic Git & GitHub"
seoTitle: "Basic Git & GitHub"
datePublished: Sat Feb 03 2024 08:33:11 GMT+0000 (Coordinated Universal Time)
cuid: cls5th5ug00030ajr83bte5o3
slug: day-8-basic-git-github
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/wX2L8L-fGeA/upload/685a4aa9f90a427aa8e674d4564d5eea.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1706942627034/5c84a48f-b54f-49b1-acfb-43a2ee6b07fd.png
tags: cloud, docker, aws, github, git, devops, hashnode, 2articles1week, technical-writing-1, devops-articles, devops-journey, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge, devopscommunity

---

## Introduction

In this blog, we are gonna have an overview of Git and GitHub, understand their differences and dive deep into it. Along with that we will delve into the world of version control, explore some major types of version controls and their pros and cons. To sum it up, we'll have an interactive practice session for our hands on practice by the end of this blog. So let's just jump into it.

## Git & GitHub

### What is git?

Git is a distributed version control system that is used for tracking changes made to a file or a set of files and allows multiple users to collaborate and work together on a file. Mostly it is used by software developers to track the changes made in their codes, collaborating with multiple developers to make software better and controlling the version.

But it can be used by anyone in any field because it is set to track changes made to a given set of file.

**Benefits**:

* *Track changes made in a file*: This includes a record of who made changes to what part of a file.
    
* *Revert any change*: Suppose someone made an unsuitable change, with the help of git you can revert the changes to the previous version of that file.
    
* *Collaboration made easy*: Git makes it easy to collaborate with others, as you can share changes and merge the changes made by different people into a single version of a file.
    

### What is GitHub?

GitHub is a web-based platform that provides hosting for distributed version control by Git. It provides all the functions of git such as distributed version control, source code management and few more features.

GitHub is simply Git on Web. Mostly it is used by developers as it made collaborating and version control easier with more user friendly features and it is also used for hosting open-source projects.

## Version Control

![](https://miro.medium.com/v2/resize:fit:1358/1*7xmUxZhEF_lkgAEJQcvNKw.jpeg align="center")

Version control is a system that tracks changes to a file or set of files over time. Its functionality includes comparing changes over time, bug fixes and recalling specific versions later. It allows us to revert files back to their previous state, revert the entire project back to a previous state or version, compare changes over time, see who last modified something that might be causing a problem, who introduced an issue and when, and more.

Suppose someone made a change to a Windows Software by Microsoft in its latest update and it started causing a problem. So the developers can revert the entire version to its previous state or previous version. This will fix the errors and later they can release new version. So this is how version control works.

### Types of Version Control:

There are two main types of version control systems: centralized version control systems and distributed version control systems.

1. **<mark>Centralized version control system (CVCS)</mark>**: In a centralized version control system, a server works as the main centralized repository which stores every version of code. The developers can commit directly to the main branch. So this is basically useful for smaller projects.
    
    Read more, [Here](https://about.gitlab.com/topics/version-control/what-is-centralized-version-control-system/).
    
2. **Distributed Version Control System (DVCS)**: In a distributed version control system, the users have the freedom to clone the entire repository into their local machine. They can make certain changes according to their will and commit the changes to their local repository. After that in order to merge it with the man repository, the user raise request the "master" branch called "**Pull-Request**" to merge their changes, and then commit the changes.
    
    The master will then check the Pull-request and "merge" the changes to the master branch.
    
    **<mark>NOTE:</mark>** The cloned repository is disconnected from the main repository. No changes made on the cloned repo will show on the main repo unless raised a pull request and merged.
    

### DVCS vs CVCS

Here are the major differences between Distributed version control and Centralized Version control :

| **Distributed Version Control (DVCS)** | **Centralized Version Control (CVCS)** |
| --- | --- |
| Each user has a complete copy of the repo. | Users check out a working copy from the central repo. |
| No heavy reliance on network connectivity. | Requires network connection for most operations. |
| Users can work offline with a local copy. | Offline work is limited, as constant connection to the central repo is needed. |
| Each local copy serves as a complete backup. | Central repo is the single point of backup. |
| Faster and more flexible branching and merging. | Branching and merging may be slower and less flexible. |
| Enables parallel development with ease. | Parallel development may face more challenges. |
| Git, Mercurial, Bazaar | CVS, SVN |

Overall, the decentralized nature of a DVCS allows for greater collaboration, flexibility, and security, making it a popular choice for many teams.

### Tasks:

Before Moving forward, here are some tasks you need to perform:

## Task:

* Install Git on your computer (if it is not already installed).
    
* Create a free account on GitHub (if you don't already have one). You can sign up at [https://github.com/](https://github.com/)
    
* Learn the basics of Git by reading the [GitHub docs](https://docs.github.com/en/get-started/using-git/about-git). This will give you an understanding of what Git is, how it works, and how to use it to track changes to files.
    

###   
Exercises:

1. Create a new repository on GitHub and clone it to your local machine
    
2. Make some changes to a file in the repository and commit them to the repository using Git
    
3. Push the changes back to the repository on GitHub
    

## Solution:

1. **Create a repository on GitHub**
    
    Click the + sign at the top right corner to create a new repository. Repositories are like your code folders online.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706946929233/d291a987-d778-4d39-aef4-177a60c84bb9.png align="center")
    
    You will get a Prompt like this and you can name your repo. I have named it `Practice_repo` .
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706947072038/16003e17-d313-4444-b37d-1c23a4f13845.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706947095389/de8c8e72-f940-4cc3-92e2-7f3ca0046d7a.png align="center")
    
    Name your repository and give it a description (this is optional).
    
    Click the "Create repository" button to create the repository. You will be prompted to this page:
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706947350215/114f5cbf-8d4c-4725-92de-72d83f82a94a.png align="center")
    
    Cloning the repo :
    
    Copy the HTTPS and use `git clone` command followed by the https address to clone the repo in your local repository.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706947658141/48166b13-6044-456c-b68c-81ecf9b3d208.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706947689657/85fab075-b427-445a-a9e8-4c3657354d7f.png align="center")
    
    The Repo is cloned in your local system.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706947732425/f6ca7c54-08d3-489e-a66c-72c2377657a5.png align="center")
    
2. Making changes in the README.md file and commit the changes.
    
    To make the changes we need to move to the `Practice_repo` directory first where the file is located.
    
    Use `cd` command.
    
    Now Edit the README.md file and save the changes
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706948051981/be082686-1f80-494b-9a29-f800416ea671.png align="center")
    
    Now, use the following commands to push it to your repo:
    
    `git init` : This will initialize git in your local repo.
    
    `git add .`: This will add all the files to the staging area.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706948376880/c99da1d6-ee21-4fab-a023-b757df4087d1.png align="center")
    
    `git commit -m "first commit"` : This will commit the code with the message first commit.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706948418053/1ad1b881-9323-4bbb-b56f-99faf1ce358f.png align="center")
    
    `git branch -M main` : For the branch we want to push.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706948458909/10624a75-df00-4707-9b9f-f42b78c7171d.png align="center")
    
    `git remote add origin` [`https://github.com/C0dewordSky/Practice_repo.git`](https://github.com/C0dewordSky/Practice_repo.git) : This will connect your local machine to your repo on GitHub. In case you cloned the repo, it will already exist.
    
3. `git push -u origin main :` Command to push to your repo
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706948561766/62523d40-23e2-4490-a796-a7b9417cdcce.png align="center")
    
    Successfully Pushed to the GitHub repo. Now Verify
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706948638545/b6b65604-7ac4-407d-9ce0-2d46636eed24.png align="center")
    
    Now you can see the changes are quickly shown on the GitHub repository.
    

<mark>You can use my GitHub repo to practice your GitHub skills. Here's the </mark> [<mark>link</mark>](https://github.com/C0dewordSky/Practice_repo)<mark>. See you around.</mark>

## Conclusion

In this blog we explored Git and GitHub - important tools for model manipulate and collaborative coding. Git, a dispensed device, allows for higher trade tracking and collaboration, at the same time as GitHub, its internet-based totally counterpart, optimizes the person experience. Understanding model manage is fundamental to venture fulfillment, and the distinction among centralized (CVCS) and dispensed (DVCS) structures is essential. DVCS, with examples like Git and Mercurial, offers rapid conversion and branching for offline work. GitHub makes it clean to host open-source initiatives. Git and GitHub adoption simplifies development, provides collaboration and powerful model manage. Whether you're an experienced developer or new to model manipulate, these tools are your gateway to collaborative coding success!

Ending this with a quote:

> Every line of code is a step toward progress. Embrace the challenge, celebrate the small victories, and remember: your code has the power to create, innovate, and inspire change

Happy Learning.