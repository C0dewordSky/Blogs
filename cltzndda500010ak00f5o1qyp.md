---
title: "TerraWeek Day 3: Dive into Terraform Workflows"
seoTitle: "TerraWeek Day 3: Dive into Terraform Workflows"
datePublished: Wed Mar 20 2024 10:15:04 GMT+0000 (Coordinated Universal Time)
cuid: cltzndda500010ak00f5o1qyp
slug: terraweek-day-3-dive-into-terraform-workflows
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1710929639047/e26d6bed-dd51-43ac-af2e-e9b710c013ec.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1710929690096/963c1fca-8073-4292-9926-887924aa3dc7.png
tags: docker, aws, kubernetes, containers, terraform, technical-writing-1, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge, terraweekchallenge

---

## Introduction

Welcome back to TerraWeek! Today, we'll delve deeper into the practical aspects of Terraform by tackling a series of exercises that showcase its capabilities in managing infrastructure as code.

**Task 1: Defining Resources**

Our first task involves creating a Terraform configuration file. This file defines the infrastructure resources we want to manage, including services like AWS EC2 instances, Azure storage accounts, or Google Compute Engine VMs. Here's an example configuration for an AWS EC2 instance:

Terraform

```bash
# Configure the AWS provider
provider "aws" {
  region = "us-east-1"
}

# Define an EC2 instance resource
resource "aws_instance" "web_server" {
  ami           = "ami-0e784e2a723e9f511"  # Amazon Machine Image ID
  instance_type = "t2.micro"
}
```

This configuration defines an AWS provider specifying the region and then creates an EC2 instance resource named "web\_server" using a specific Amazon Machine Image (AMI) and instance type.

**Task 2: Verifying Configuration with State and Validation**

Before applying changes to your infrastructure, it's crucial to verify your Terraform configuration. Terraform uses state files to track the managed resources. Here's how to check and validate your configuration:

1. **Check State Files (Optional):**
    
    * `terraform state list`: This command lists the managed resources defined in your Terraform configuration. (Output: List of managed resources and their attributes)
        
2. **Validate Configuration:**
    
    * `terraform validate`: This command validates your Terraform configuration for errors. (Output: If successful, it displays "Success! Terraform configuration valid" or lists any errors encountered)
        

**Task 3: Automating Configuration with Provisioners**

Terraform allows adding provisioners to your configuration. These are scripts or tools that run on the created resources to configure them after deployment. Let's modify our EC2 instance configuration to install a web server using a user data script:

Terraform

```bash
resource "aws_instance" "web_server" {
  # ... existing configuration ...

  # User data script to install a web server
  user_data = <<EOF
    sudo yum update -y
    sudo yum install httpd -y
    sudo systemctl start httpd
    sudo systemctl enable httpd
  EOF
}
```

Here, the `user_data` block defines a script that installs and starts a web server after the instance creation. Now, to apply these changes:

* `terraform apply`: This command applies the configuration to your infrastructure, creating the resources and running any provisioners defined. (Output: Shows the changes being made and prompts for confirmation)
    

**Task 4: Managing Resource Lifecycle**

Terraform allows managing the lifecycle of resources through lifecycle management configurations. These configurations define actions to be taken during resource creation, modification, or deletion. Let's add a lifecycle management block to our configuration to automatically stop the instance before deletion:

Terraform

```bash
resource "aws_instance" "web_server" {
  # ... existing configuration ...

  lifecycle {
    pre_delete {
      execute "stop-instance", <<EOF
        aws ec2 stop-instances --instance-ids ${self.id}
      EOF
    }
  }
}
```

This configuration defines a `pre_delete` lifecycle block that executes a script to stop the EC2 instance before it's deleted. To apply this change and then remove the resource:

* `terraform apply`: Apply the changes, including the lifecycle management configuration. (Output: Shows changes being made)
    
* `terraform destroy`: This command removes the resources managed by Terraform. The lifecycle management pre-delete script will stop the instance before deletion. (Output: Shows the resources being destroyed)
    

**Conclusion**

By following these tasks, you've gained practical experience in defining resources, verifying configurations, automating configurations using provisioners, and managing resource lifecycles with Terraform. Remember, these are just a glimpse of Terraform's capabilities. As you continue your Terraform journey, explore its vast features to streamline your infrastructure management and automate deployments effectively.

Happy Learning.