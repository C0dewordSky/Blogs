---
title: "Day 27 - Jenkins Declarative Pipeline Project"
seoTitle: "Jenkins Declarative Pipeline Project "
datePublished: Thu Feb 22 2024 08:49:26 GMT+0000 (Coordinated Universal Time)
cuid: clswzf8ht000108l9ejed89t7
slug: day-27-jenkins-declarative-pipeline-project
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1708591580921/b4294b0d-0440-4260-9545-6ef20ffc1844.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1708591748570/e9ffef89-a461-427c-849d-835e2479a2e2.png
tags: docker, aws, projects, kubernetes, devops, jenkins, cicd-cjy1vtdk2005kjjs17n8couc3, 2articles1week, technical-writing-1, devops-articles, devops-journey, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge, devopscommunity

---

## Introduction

Welcome DevOps enthusiasts. In this blog we will be revisiting the project "Todo-app" once again and create a Pipeline, but this time using Declarative Pipeline. This will be a short one, so without any further ado, let's begin building.

# Task-01

* Create a docker-integrated Jenkins declarative pipeline
    
* Use the above-given syntax using `sh` inside the stage block
    
* You will face errors in case of running a job twice, as the docker container will be already created, so for that do task 2
    

# Task-02

* Create a docker-integrated Jenkins declarative pipeline using the `docker` groovy syntax inside the stage block.
    
* You won't face errors, you can Follow [this documentation](https://tempora-mutantur.github.io/jenkins.io/github_pages_test/doc/book/pipeline/docker/)
    
* Complete your previous projects using this Declarative pipeline approach
    

## Solution Blueprint

### Task 1

Creating a docker-integrated declarative pipeline with shell commands

```bash
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker pull todo-app:latest'
            }
        }
        stage('Test') {
            steps {
                sh 'docker run todo-app:latest echo "Hello, Docker!"'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker run todo-app:latest echo "Deploying..."'
            }
        }
    }
}
```

### Task 2

Creating a docker-integrated declarative pipeline with Groovy Script

```bash
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    docker.image('todo-app:latest').pull()
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    docker.image('todo-app:latest').run('echo', 'Hello, Docker!')
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    docker.image('toso-app:latest').run('echo', 'Deploying...')
                }
            }
        }
    }
}
```

Here's the Blueprint of solution of Project mentioned in [**Blog 24**](https://hashnode.com/post/clssrbzu8000i09jo4h1e13n6). Recreate the Project and share it on LinkedIn.

NOTE: A detailed blog about the project will come soon.

### Conclusion

In this weblog, we revisited our Todo-app project and confirmed how to create Jenkins declarative pipelines with Docker integration the usage of two extraordinary procedures.

For Task 01, we utilized the sh syntax within the level blocks to interact with Docker. This approach is easy but may come upon errors whilst jogging the task multiple instances because of present Docker packing containers.

For Task 02, we hired the Docker Groovy syntax in the stage blocks. This technique presents more manage and versatility, ensuring smooth execution without errors even when going for walks the task more than one times.

By embracing the declarative pipeline method, we've streamlined our CI/CD process, making it more effecient and maintainable. With Docker integration, we make certain consistency throughout distinct environments, permitting seamless testing and deployment of our Todo-app.

Stay tuned for an in depth blog about this undertaking, where we're going to dive deeper into its architecture, implementation information, and fine practices. Don't forget to proportion your thoughts and studies with us on LinkedIn.

I hope this blog added some value to your learning. Ending this with a quote

> Be like a postage stamp. Stick to one thing until you get there. - Josh Billings

Happy Learning