---
title: "Day 1 - Terraform Week"
seoTitle: "Day 1 - Terraform Week "
datePublished: Mon Mar 18 2024 12:12:23 GMT+0000 (Coordinated Universal Time)
cuid: cltwwoja3000508jnh0srehuu
slug: day-1-terraform-week
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1710763849359/d0cb96f3-da58-40ce-aabe-c385fb36e6e4.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1710763923395/88203fd3-65bb-4b45-a2bf-40a61ff87940.png
tags: aws, azure, devops, terraform, gcp, terraform-state, terraform-cloud, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge, tws, terraweek, terraweekchallenge

---

## Introduction

Welcome to TerraWeek Day 1! In this blog series, we will dive into the world of Terraform and explore how it revolutionizes infrastructure management through code. Whether you're a seasoned DevOps engineer or just starting your journey in cloud computing, understanding Terraform is crucial for efficient and scalable infrastructure deployment.

## Introduction to Terraform and Terraform Basics

* What is Terraform and how can it help you manage infrastructure as code?
    
* Why do we need Terraform and how does it simplify infrastructure provisioning?
    
* How can you install Terraform and set up the environment for AWS, Azure, or GCP?
    
* Explain the important terminologies of Terraform with the example at least (5 crucial terminologies).
    

## Solution:

### Terraform:

Terraform is a infrastructure building tool that builds the infrastructure of our deployment via code. It is also called as an Infrastructure as Code(IAC) tool. It helps you build, change and version infrastructure in the safest way possible.

This includes low-level components like compute instances, storage, and networking; and high-level components like DNS entries and SaaS features.

**Benefits:**

* The first major benefit is that it let's us build the infrastructure, without any physical intervention and going through the long process of setting up a desired infrastructure, as code.
    
* It prevents human errors.
    
* It is faster in deploying the infrastructure.
    

**Why do we need terraform and how does it simplifies infrastructure provisioning?**

Here are the main reasons for using Terraform and how it simplifies infra provisioning.

1. **Declarative Configuration Language**: Terraform uses a declarative language called HashiCorp Configuration Language (HCL) to define the desired state of your infrastructure. With HCL, you describe the resources, providers, and configurations needed for your infrastructure.
    
2. **Resource Providers**: Terraform supports various cloud providers (like AWS, Azure, Google Cloud), as well as other infrastructure components such as Docker, Kubernetes, and databases. Each provider has its set of resources that you can manage using Terraform.
    
3. **Desired State Management**: Terraform works based on the concept of desired state. You define the desired state of your infrastructure in the Terraform configuration files (usually with a `.tf` extension), and Terraform ensures that the actual state of your infrastructure matches the desired state.
    
4. **Infrastructure as Code (IaC)**: By using Terraform, you treat your infrastructure configurations as code. This means you can version control your infrastructure, collaborate with team members using version control systems like Git, and apply software development practices such as code reviews, testing, and automated deployments to your infrastructure configurations.
    
5. **Modularity and Reusability**: Terraform allows you to create modular and reusable infrastructure components called modules. Modules encapsulate specific functionalities or resources, making it easier to manage and scale your infrastructure in a structured and organized manner.
    
6. **State Management**: Terraform maintains a state file (usually named `terraform.tfstate`) that keeps track of the current state of your infrastructure. This state file is crucial for Terraform to determine what changes need to be applied to move from the current state to the desired state.
    
7. **Execution Plans and Automation**: When you run Terraform commands (such as `terraform plan` or `terraform apply`), Terraform generates an execution plan that outlines what actions it will take to reach the desired state. This helps you understand the changes before applying them, reducing the risk of unintended modifications to your infrastructure.
    
8. **Cloud-agnostic**: While Terraform supports various cloud providers, it also allows you to build infrastructure that spans multiple clouds or on-premises environments. This provides flexibility and avoids vendor lock-in.
    

### Installing Terraform on popular cloud providers:

To install Terraform and set up the environment for AWS, Azure, or GCP, follow these general steps:

1. **Install Terraform**:
    
    * Download the Terraform binary suitable for your operating system from the official Terraform website: [Terraform Downloads](https://www.terraform.io/downloads.html)
        
    * Extract the downloaded archive and move the `terraform` binary to a directory included in your system's PATH variable (e.g., `/usr/local/bin` for Linux or macOS).
        
2. **Configure AWS, Azure, or GCP Credentials**:
    
    * **AWS**: Set up AWS credentials by configuring the AWS CLI (`aws configure`) or by setting the `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY` environment variables.
        
    * **Azure**: Install the Azure CLI and log in (`az login`) to authenticate with your Azure account. Terraform will use the Azure CLI credentials for authentication.
        
    * **GCP**: Set up a service account key for Terraform to authenticate with Google Cloud. Download the JSON key file and set the `GOOGLE_APPLICATION_CREDENTIALS` environment variable to point to this file.
        
3. **Create Terraform Configuration Files**:
    
    * Create a directory for your Terraform project and navigate to it.
        
    * Create a new `.tf` file (e.g., [`main.tf`](http://main.tf)) where you'll define your Terraform configurations for AWS, Azure, or GCP resources.
        
4. **Write Terraform Configurations**:
    
    * Inside your `.tf` file, define the provider and resources specific to the cloud platform you're working with. Here are examples for each cloud:
        
        **AWS Example (**[`main.tf`](http://main.tf)):
        
        ```bash
        provider "aws" {
          region = "us-west-2"
        }
        
        resource "aws_instance" "example_instance" {
          ami           = "ami-0c55b159cbfafe1f0"
          instance_type = "t2.micro"
          tags = {
            Name = "ExampleInstance"
          }
        }
        ```
        
        **Azure Example (**[`main.tf`](http://main.tf)):
        
        ```bash
        provider "azurerm" {
          features {}
        }
        
        resource "azurerm_virtual_machine" "example_vm" {
          name                  = "example-vm"
          location              = "East US"
          resource_group_name   = "example-resources"
          vm_size               = "Standard_DS1_v2"
        
          storage_image_reference {
            publisher = "Canonical"
            offer     = "UbuntuServer"
            sku       = "16.04-LTS"
            version   = "latest"
          }
        
          os_profile {
            computer_name  = "example-vm"
            admin_username = "adminuser"
          }
        
          admin_password = "P@ssw0rd1234!"
        }
        ```
        
        **GCP Example (**[`main.tf`](http://main.tf)):
        
        ```bash
        provider "google" {
          credentials = file("path/to/your/credentials.json")
          project     = "your-project-id"
          region      = "us-central1"
        }
        
        resource "google_compute_instance" "example_instance" {
          name         = "example-instance"
          machine_type = "n1-standard-1"
          zone         = "us-central1-a"
        
          boot_disk {
            initialize_params {
              image = "debian-cloud/debian-10"
            }
          }
        
          network_interface {
            network = "default"
            access_config {
              // Ephemeral IP
            }
          }
        }
        ```
        
5. **Initialize Terraform**:
    
    * Open a terminal or command prompt in your Terraform project directory.
        
    * Run `terraform init` to initialize Terraform and download necessary provider plugins.
        
6. **Apply Terraform Configurations**:
    
    * After initializing, run `terraform plan` to see the execution plan.
        
    * If the plan looks good, apply the configurations with `terraform apply`. Confirm by typing `yes` when prompted.
        

### Explain the important terminologies of Terraform with the example:

Terminologies in Terraform along with examples to help you understand them better:

1. **Provider**:
    
    * Definition: A provider is responsible for managing the lifecycle of a particular type of infrastructure resource. <mark>Providers interact with APIs of various infrastructure platforms (e.g., AWS, Azure, Google Cloud) to create, update, and delete resources.</mark>
        
    * Example: In the case of AWS, the provider block in Terraform configuration would look like this:
        
        ```bash
        provider "aws" {
          region = "us-west-2"
        }
        ```
        
2. **Resource**:
    
    * Definition: <mark>A resource represents a single piece of infrastructure,</mark> such as a virtual machine, network interface, or database instance. Resources are declared within Terraform configuration files and are managed by the corresponding provider.
        
    * Example: Creating an AWS EC2 instance using Terraform would look like this:
        
        ```bash
        resource "aws_instance" "example_instance" {
          ami           = "ami-0c55b159cbfafe1f0"
          instance_type = "t2.micro"
          tags = {
            Name = "ExampleInstance"
          }
        }
        ```
        
3. **Module**:
    
    * Definition: <mark> A module is a reusable and encapsulated collection of Terraform configurations that represent a set of related resources.</mark> Modules promote modularity, reusability, and maintainability of infrastructure code.
        
    * Example: <mark>Creating a module for managing an AWS S3 bucket could look like this:</mark>
        
        ```bash
        module "s3_bucket" {
          source  = "terraform-aws-modules/s3-bucket/aws"
          version = "1.0.0"
          bucket_name = "example-bucket"
          acl         = "private"
        }
        ```
        
4. **State**:
    
    * Definition: State refers to the current state of your infrastructure as tracked by Terraform. The state file (`terraform.tfstate`) contains information about the resources managed by Terraform, their attributes, dependencies, and metadata.
        
5. **Plan and Apply**:
    
    * Definition: Planning and applying are key actions in Terraform's workflow. When you run `terraform plan`, Terraform generates an execution plan that shows the changes it will make to reach the desired state. Running `terraform apply` then applies those changes to your infrastructure.
        
    * Example: After making changes to your Terraform configurations, you can run:
        
        ```bash
        terraform plan
        ```
        
        This will show you a preview of the changes that Terraform will apply. If the plan looks good, you can apply the changes with:
        
        ```bash
        terraform apply
        ```
        
        Terraform will then execute the planned changes and update your infrastructure accordingly.
        

These terminologies form the foundation of Terraform's language and workflow, allowing you to effectively manage infrastructure as code with clarity and control.

## Conclusion

Congratulations on completing Day 1 of TerraWeek! We've covered the fundamentals of Terraform, including its purpose, installation, environment setup, and important terminologies.

Stay tuned for Day 2, where we'll delve deeper into advanced Terraform concepts and best practices. Don't forget to share your learnings on LinkedIn and connect with me for further guidance.

Keep learning! 🚀