---
title: "Terraform Week Day 2: Diving into HCL Syntax"
seoTitle: "Terraform Week Day 2: Diving into HCL Syntax"
datePublished: Tue Mar 19 2024 14:46:47 GMT+0000 (Coordinated Universal Time)
cuid: cltyhmxxg000408jo7ddn5t1d
slug: terraform-week-day-2-diving-into-hcl-syntax
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1710859532478/39d25c7a-672d-4319-93f2-b1485fa96190.png
tags: docker, aws, kubernetes, hashnode, containers, terraform, technical-writing-1, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge, terraweekchallenge

---

## Introduction

Welcome back to Terraform Week! Yesterday, we got acquainted with the basics of Terraform. Today, we'll delve deeper into the world of HashiCorp Configuration Language (HCL), the language that forms the backbone of Terraform configurations.

### Task 1: Mastering the Building Blocks

HCL is a human-readable language designed for defining infrastructure as code. Here's what you need to understand to work effectively with HCL in Terraform:

* **HCL Blocks:** Imagine building blocks for your infrastructure. HCL blocks group related configurations. Think of them as sections in your code, defining resources, providers, and variables.
    
* **Parameters and Arguments:** Within these blocks, you'll encounter parameters and arguments. Parameters are pre-defined attributes specific to each block, while arguments provide values for those parameters, customizing your infrastructure.
    

```bash
<Block> <Parameters>{
<arguments>
}
```

Beyond these core concepts, Terraform offers a rich ecosystem of resources and data sources:

* **Resources:** These are the building blocks of your infrastructure. Terraform provides resources for creating anything from virtual machines to databases across various cloud providers and on-premises solutions.
    
* **Data Sources:** Think of data sources as external information providers. They allow you to retrieve data from various sources and use it within your Terraform configuration.
    

**Getting Started Resources:**

* Terraform HCL Syntax Overview: [https://developer.hashicorp.com/terraform/language/syntax](https://developer.hashicorp.com/terraform/language/syntax)
    
* Terraform Resources Documentation: [https://registry.terraform.io/](https://registry.terraform.io/)
    

### Task 2: Variables - Reusable Configuration Magic

Imagine defining configurations repeatedly. Not ideal, right? Variables come to the rescue!

* **Creating a Variables File:** Create a file named `variables.tf` to store reusable configuration values.
    
* **Defining Variables:** Within `variables.tf`, use the `variable` keyword followed by a name and data type (e.g., `string`, `number`) to define a variable.
    

Now, in your main configuration file (`main.tf`), you can use the defined variable to create resources. Terraform will replace the variable name with its corresponding value throughout your configuration.

**Example:**

Terraform

```bash
// variables.tf
variable "region" {
  type = string
}

// main.tf
resource "local_file" "my_config" {
  filename = var.region + "/config.txt"
  content  = "This is my configuration file content"
}
```

In this example, we define a variable `region` in `variables.tf` and use it within the `filename` argument of the `local_file` resource in `main.tf`.

### Task 3: Putting it All Together - Practice Makes Perfect!

Now that you understand the basics of HCL syntax and variables, let's get your hands dirty with some practical exercises:

* **Required Providers:** Terraform interacts with various platforms and services through providers. Add a `required_providers` block to your configuration, specifying the provider and its version (e.g., `docker`, `aws`).
    
* **Testing Your Configuration:** Terraform provides a powerful command-line interface (CLI) for managing your configurations. Use the `terraform init` command to download required providers and initialize your workspace. Subsequently, use `terraform plan` to preview the changes your configuration will make before applying them with `terraform apply`.
    

**Additional Resources:**

* Terraform Providers Documentation: [https://registry.terraform.io/](https://registry.terraform.io/)
    
* Terraform CLI Commands: [https://developer.hashicorp.com/terraform/cli/commands/init](https://developer.hashicorp.com/terraform/cli/commands/init)
    

## Conclusion

Remember, practice is key! Experiment with different resources, data sources, and variables to solidify your understanding of HCL syntax and Terraform configuration. Don't hesitate to consult the official documentation or online communities for further guidance as you progress on your Terraform journey.