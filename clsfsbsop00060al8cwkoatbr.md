---
title: "Day 15 - Python Libraries"
seoTitle: "Python Libraries"
datePublished: Sat Feb 10 2024 07:58:43 GMT+0000 (Coordinated Universal Time)
cuid: clsfsbsop00060al8cwkoatbr
slug: day-15-python-libraries
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/D9Zow2REm8U/upload/215e9bb1af3dab8f1be1572b3188ad92.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1707551898541/b299bd4c-1f73-4125-81a9-593065bc42ab.png
tags: docker, aws, python, kubernetes, python3, devops, 2articles1week, technical-writing-1, python-beginner, devops-articles, devops-journey, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge, devopscommunity

---

## Introduction

Hey fellow DevOps enthusiasts! Today we are going to dive into the world of file parsing using Python, an essential skill for any DevOps Engineer. Whether you’re dealing with JSON, YAML, or even good old-fashioned text files, understanding how to properly parse them can save you a lot of time and trouble in your daily tasks. Also, as a tradition, we'll be solving some scenario based question by the end of this blog. So without any delay, Let's begin.

### **Python's role in DevOps:**

Put yourself in this scenario: imagine that you have a complex infrastructure to manage, including servers, networks, databases, and more. How overwhelming would it be to handle all of that manually? It would be a nightmare!

But fear not, because Python is here to save the day with its powerful scripting capabilities. With Python, DevOps engineers can automate tasks, integrate systems, and greatly simplify their work.

### Libraries

![](https://ajaytech.co/wp-content/uploads/2019/05/python_standard_libraries-1.png align="center")

First, let’s talk about libraries. So Python provides many libraries for DevOps projects, and some common ones are `os`, `sys`, `json`, and `yaml`. Others also include libraries for Ansible, Terraform Boto3 etc. These libraries are like tools in your DevOps toolbox, each serving a specific purpose and making your life easier.

There are many libraries, but hold on, we'll get to know about them in detail in the upcoming days, so no need to worry.

Well here's a brief Knowledge about few of them so let's just begin**:**

**1\.** `os` Library:

The `os` library provides a ton of features for interacting with the running machine, execute all the obligations including document manipulation, listing operations, and environment variables management. Below are a few examples showcasing its talents:

```python
import os

# Check if a document exists
if os.Route.Exists('document.Txt'):
    print("File exists!")

# List all documents in a listing
files = os.Listdir('/route/to/listing')
print("Files in listing:", documents)

# Get the modern running directory
cwd = os.Getcwd()
print("Current working directory:", cwd)
```

**2\.** `sys` Library:

The `sys` library exposes device-unique parameters and features, enabling DevOps professionals to engage with the Python interpreter and manage runtime environment settings. Here are some usage eventualities:

```python
import sys

# Get command-line arguments
arguments = sys.Argv
print("Command-line arguments:", arguments)

# Exit the program with an mistakes code
sys.Exit(1)
```

**3\.** `json` Library:

The `json` library executes the encoding and interpreting of JSON (JavaScript Object Notation) facts, a ubiquitous format for changing based records. Let's discover its functionality:

```python
import json

# Encode Python records to JSON
facts = "name": "John", "age": 30
json_data = json.Dumps(records)
print("JSON information:", json_data)

# Decode JSON information to Python
json_str = '"name": "Alice", "age": 25'
decoded_data = json.Masses(json_str)
print("Decoded data:", decoded_data)
```

Read about JSON, [Here](https://www.json.org/json-en.html).

**4\.** `yaml` Library:

Yet Another Markup Language. The `yaml` library empowers builders to paintings with YAML (YAML Ain't Markup Language) documents, a human-readable data serialization format. It gives strategies for parsing and serializing YAML statistics systems:

```python
import yaml

# Parse YAML facts
yaml_str = """
call: Bob
age: 35
"""
parsed_data = yaml.Safe_load(yaml_str)
print("Parsed information:", parsed_data)

# Serialize Python statistics to YAML
statistics = "call": "Eve", "age": forty
yaml_data = yaml.Unload(information)
print("YAML records:", yaml_data)
```

## Scenario based Practice

**Scenario**:

You're tasked with growing a script that interacts with numerous cloud carrier vendors' records stored in one of a kind formats.

The first component includes growing a Python dictionary and saving it as a JSON report.

The 2nd component includes studying a JSON report containing information approximately cloud services offered by means of specific vendors and extracting the service names.

Additionally, you want to put into effect functionality to transform YAML data to JSON format.

## Solution:

**Task 1**: Creating Dictionary and Writing to JSON

You're required to increase a Python script that creates a dictionary representing extraordinary cloud service vendors together with their services and saves this dictionary to a JSON document.

```bash
# Task 1: Create a Python Dictionary and Write to JSON File
cloud_services = {
    "aws": "ec2",
    "azure": "VM",
    "gcp": "compute engine"
}

import json

with open("services.json", "w") as json_file:
    json.dump(cloud_services, json_file)
```

**Task 2**: Reading JSON File and Printing Service Names

You want to extend the script to examine the services.json report and print the provider names presented through each cloud service company.

```bash
# Task 2: Read JSON File and Print Service Names
with open("services.json", "r") as json_file:
    data = json.load(json_file)

for provider, service in data.items():
    print(f"{provider}: {service}")
```

**Task 3**: Reading YAML File and Converting to JSON

Finally, implement capability to read a YAML record named services.yaml, convert its contents to JSON, and print the converted JSON records.

```bash
# Task 3: Read YAML File and Convert to JSON
import yaml

with open("services.yaml", "r") as yaml_file:
    yaml_data = yaml.safe_load(yaml_file)

json_data = json.dumps(yaml_data, indent=4)
print(json_data)
```

## **Conclusion**

In this short blog, we gained knowledge about few important libraries. These libraries can help a DevOps experts to navigate the intricacies of document parsing in Python with self notion and scalability. Whether manipulating documents, interacting with the gadget, or coping with structured information formats like JSON and YAML, those libraries characteristic crucial gadget within the arsenal of current infrastructure management. I hope this blog added some value to your learning.

Ending this with a quote

> Climb mountains not so the world can see you, but so you can see the world. - David McCullough Jr.

Happy Learning