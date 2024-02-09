---
title: "Day 14 - Python Data Types and Data Structures"
seoTitle: "Python Data Types and Data Structures"
datePublished: Fri Feb 09 2024 07:44:52 GMT+0000 (Coordinated Universal Time)
cuid: clsece4qo000i09ifhzg6fs96
slug: day-14-python-data-types-and-data-structures
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707423432358/c7b0d668-f734-459e-a5d7-d749066b66b6.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1707423811509/c4f12fa2-18ca-4d2d-ae36-8b28afd3bef9.png
tags: programming-blogs, linux, docker, aws, python, kubernetes, python3, devops, 2articles1week, technical-writing-1, python-beginner, devops-articles, devops-journey, trainwithshubham, devopscommunity

---

## Introduction

Hello, DevOps enthusiasts! On Day 14 of our expedition, we will explore the nuances that surround Python's data types and structures. These are fundamental elements in achieving excellence as programmers. Let us come together to navigate through the intricate terrain of Python programming while uncovering vital principles essential to coding success.

### Data Types

Python's data types form the basis of our algorithms and dictate allowable operations while adding structure to our programs. To understand their functionality, let us explore some of Python's available data types.

**Numeric**: These data types include integers, floating-point numbers, and complex numbers which enable precise numerical computation.

```bash
age = 27
pi = 3.14
complex_number = 2 + 3j
```

The variable "age" is assigned a value of 27. The constant pi is assigned the value of 3.14. Lastly, the variable "complex\_number" has been set to equal 2 plus imaginary number 3j.

**Sequential**: Data types such as strings, lists and tuples are sequential in nature. These ordered collections of elements provide a flexible means for manipulating data.

```bash
name = "Alice"
my_list = [1, 2, 3, 4, 5]
my_tuple = (6, 7, 8)
```

The variables 'name', 'my\_list', and 'my\_tuple' have been assigned the values "Alice", \[1, 2, 3, 4, 5\], and (6 ,7 ,8) respectively in Python.

**Boolean**: The Boolean data types encompass logical values that depict either True or False, and are of great importance in decision-making within algorithms.

```python
learning_is_ongoing = True
```

**Set**: A set is a collection of unique elements that are not ordered, which allows for the execution of set operations and guarantees data integrity.

```python
numbers_with_no_duplicates = set([1, 2, 3, 4, 5])
```

**Dictionaries**: Dictionaries demonstrate the association of values with keys, creating a streamlined approach for accessing data based on distinct identifiers.

```python
data = {"name": "Bob", "age": 30, "job": "DevOps Engineer"}
```

## Data Structures

![](https://miro.medium.com/v2/resize:fit:746/1*VdLFpmSutr5BSbEeAtpmrQ.jpeg align="center")

Alongside data types, data structures offer an effective way to organize and manipulate data. Here, we will explore some essential Built-In Python data structures.

**Lists**: Lists are similar to dynamic arrays, as they provide mutable collections that can accommodate various types of data. This makes them useful for facilitating the manipulation of dynamic data.

```python
books_i_enjoy = ["The Hobbit", "Harry Potter", "The Alchemist"]
```

**Tuple**: Tuples are sequences that cannot be changed and contain defined sets of elements. They guarantee data validity and simplify the process of iteration by increasing efficiency.

```python
size = [1920, 1080]
```

**Dictionary**: Once again, dictionaries function as associative arrays that provide key-value pairs for efficient data retrieval. They demonstrate the effectiveness of organizing data with speed and accuracy.

```bash
employee_info = {"name": "Eve", "age": 25, "department": "IT"}
```

The information of the employee named Eve includes their name, age (25), and department which is IT. This data is stored in a dictionary format using Python programming language as shown above:

## Practice

**Scenario-based question:**

You are a software engineer working on a project that requires handling different types of data structures in Python. During a team meeting, a junior developer asks you to explain the differences between lists, tuples, and sets, as they're confused about when to use each one. Your task is to provide a clear explanation and then guide them through a hands-on exercise to solidify their understanding.

### Tasks:

1. Give the Difference between List, Tuple and set. Do Handson and put screenshots as per your understanding.
    
2. Create below Dictionary and use Dictionary methods to print your favourite tool just by using the keys of the Dictionary.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707423073792/bd0f99cf-ae6d-498e-95ab-935398cae826.png align="center")
    
3. Create a List of cloud service providers eg.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707423124126/8a7f6290-77e7-4aaf-80c4-041d44a203c9.png align="center")
    

### Solution

**Task 1**:

Lists, tuples, and sets are all fundamental data structures in Python, each with its unique characteristics and use cases.

1. **List**:
    
    * Lists are ordered collections of items that allow duplicates.
        
    * They are mutable, meaning you can add, remove, or modify elements after creation.
        
    * Lists are represented by square brackets `[ ]`.
        
    * Example: `my_list = [1, 2, 3, 4, 5]`
        
2. **Tuple**:
    
    * Tuples are ordered collections of items that allow duplicates.
        
    * They are immutable, meaning once created, you cannot change the elements.
        
    * Tuples are represented by parentheses `( )`.
        
    * Example: `my_tuple = (1, 2, 3, 4, 5)`
        
3. **Set**:
    
    * Sets are unordered collections of unique items.
        
    * They do not allow duplicates, and the elements are not indexed.
        
    * Sets are represented by curly braces `{ }`.
        
    * Example: `my_set = {1, 2, 3, 4, 5}`
        

**Task 2:**

1. First, let's create and manipulate these data structures in Python.
    
2. Open a Python interpreter or a code editor and execute the following code snippets:
    

```python
# Creating a list
my_list = [1, 2, 3, 4, 5]
print("List:", my_list)

# Creating a tuple
my_tuple = (1, 2, 3, 4, 5)
print("Tuple:", my_tuple)

# Creating a set
my_set = {1, 2, 3, 4, 5}
print("Set:", my_set)
```

1. Now, let's work with dictionary methods to retrieve your favorite tool using its key:
    

```python
fav_tools = {
  1: "Linux",
  2: "Git",
  3: "Docker",
  4: "Kubernetes",
  5: "Terraform",
  6: "Ansible",
  7: "Chef"
}

# Using dictionary methods to print your favorite tool
tool_key = 3
print("My favorite tool is:", fav_tools.get(tool_key))
```

1. Finally, let's create a list of cloud service providers:
    

```python
cloud_providers = ["AWS", "GCP", "Azure"]
print("Cloud Service Providers:", cloud_providers)
```

Take screenshots of your code execution and results to document your understanding and practice and Upload it on LinkedIn to share your learnings in Public.

## Conclusion

We have finished exploring the data types and structures in Python, which has given us valuable knowledge on the fundamental components of programming with this language. Going forward, we'll dive deep in Python in the upcoming days. Let curiosity, tenacity and an unwavering commitment towards excellence be our guiding principles as we strive for expertise.

Ending this with a quote

> Success is not final, failure is not fatal: It is the courage to continue that counts. - Winston Churchill

Happy Learning