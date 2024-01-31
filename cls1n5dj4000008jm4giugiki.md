---
title: "Day 5 - Advanced Linux Shell Scripting with User management"
seoTitle: "Day 5 - Advanced Linux Shell Scripting with User management"
datePublished: Wed Jan 31 2024 10:24:59 GMT+0000 (Coordinated Universal Time)
cuid: cls1n5dj4000008jm4giugiki
slug: day-5-advanced-linux-shell-scripting-with-user-management
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1706689948810/48f197e3-84e7-4f58-ae04-827f96b1b080.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1706696672517/f143bede-7a8e-4830-b08a-7653456834b8.png
tags: linux, docker, aws, kubernetes, devops, containers, 2articles1week, technical-writing-1, linux-basics, 90daysofdevops, 90daysofdevops-chanllenge

---

![](https://www.seobility.net/en/wiki/images/c/c3/CronJob.png align="center")

### Introduction

In this blog we'll be diving deep into the concepts of shell scripting along with learning new ways to use it for automating tasks. We'll also learn about Cron and Crontab and User management in Linux. Also we'll recall the concepts learned in the past few blogs and have some hands on practice by solving some interactive scenario based questions. So let's begin learning.

### What is Cron?

Cron is a service provided by Linux which helps us in scheduling tasks and automating them. It is a Unix based job-scheduler that schedules and performs tasks according to the instruction provided to it.

Suppose we need to take keep a track and backup the logs exactly at 3 am. Instead of doing it manually, we can set a "**<mark>Cron Job</mark>**" that does it for us.

### What is a Cron Job?

A Cron Job is a set of instructions or Linux Commands given to the Cron in order to schedule tasks. It allows users to automate and perform repetitive tasks at a given time, date and frequency at which a particular command, script, or program should be executed.

Mostly it is used for keeping a track of logs, system maintenance and other routine operations, enabling users to automate processes without manual intervention.

Important: A Cron Job is managed by the cron daemon.

### What is a crontab?

A <mark>crontab</mark> is a configuration file that holds the set of instruction for a cron job. Crontab stands for “cron table" . The crontab file contains lines with scheduling information and the corresponding commands to be executed.

**Important**: Crontabs are stored in **<mark>/etc/crontab</mark>** folder.

## Understanding the Crontab Syntax

![](https://res-1.cloudinary.com/hn1xwflmv/image/upload/q_auto/v1/images/cron_expression_syntax.png align="center")

The Linux Crontab Format is represented by the following syntax:

```bash
MIN HOUR DOM MON DOW Command
```

| Field | Description | Range |
| --- | --- | --- |
| MIN | <mark>Minute</mark>. Specifies the minute for the command to run | 0-59 min |
| HOUR | Specifies the hour of the day when the command will run | 0-23 hr |
| DOM | <mark>Day of Month</mark>. Specifies the day of the month for the task. | 1-31 |
| MON | <mark>Month</mark>. For the month in which the command will run | 1-12 |
| DOW | <mark>Day of Week</mark>. Specifies the day of the week for the tasks to run. | 0 - 6 |
| Command | the actual command or script that will run at the scheduled time. | \- |

## How to set a Cron Job?

### Some basic commands:

* **<mark>crontab -e</mark>** : This command opens the crontab file in the default text editor specified by your system.
    
* **<mark>crontab -l</mark>** : This command lists all the cronjobs of the current user. It displays the contents of your crontab file, showing the scheduled tasks and their associated commands.
    
* ```bash
    crontab -l  
    
    #OUTPUT 
    
    # Example cron job
    * * * * * /path/to/your/command.sh
    ```
    

### Setting up your first cronjob:

1. Step - 1
    
    use <mark>crontab -e</mark> to open your default text editor.
    
    ```bash
    crontab -e
    ```
    
2. Step -2
    
    Write the cronjob in the syntax mentioned above. Example:
    
    ```bash
    30 14 * * * /path/to/your/script.sh
    ```
    
    This Cronjob means that the process will run at 2:30 pm on every day of the month, every month and every week.
    
3. Step - 3
    
    Save and exit the editor.
    
    The cron job is now set up, and it will run according to the schedule you defined. To View the cronjob, use <mark>crontab -l.</mark>
    
    ```bash
    crontab -l 
    ```
    

## User Management

### What is a user?

A user is an entity in Linux that has the power to execute and perform tasks on the linux machine and perform several other operations. Each user is assigned an ID that is unique for each user in the operating system.

**IMPORTAN:** ID 0 is assigned to the <mark>root user</mark> and the IDs 1 to 999 both included are assigned to the <mark>system users</mark> and hence the ids for <mark>local user</mark> begins from 1000 onwards.

### System User Vs Local User:

| System User | Local User |
| --- | --- |
| System users are created to run specific system processes or services. They are not meant for interactive logins. | Local users are created for human users who interact with the system. They may have home directories and can log in to the system. |
| No home directory | Local users usually have a home directory where they can store personal files and configurations. |
| No Interactive Login | Local users can log in and interact with the system directly |
| services like Apache, Nginx, or databases are examples of System users. | Humans who needs access to the system are example of Local Users. |

### User Management Commands:

* **Creating user**:
    
    To create a new User, use the "**<mark>useradd</mark>**" command.
    
    ```bash
    sudo useradd <username>
    ```
    
* **Setting Password for the user**:
    
    To set password for the user, use "**<mark>passwd</mark>**" command.
    
    ```bash
    sudo passwd <username>
    ```
    
    This will allow you to set the password for the given user.
    

**IMPORTANT**: Remember to use `sudo` to execute commands with administrative privileges.

## **Scenario: Bash Script Challenge**

You are tasked with creating a bash script that automates the process of creating directories with dynamic names. Your script should take three arguments: the base name of the directories, the starting number, and the ending number. Additionally, you need to create a script to set up user accounts and display their usernames.

### **Question 1: Directory Creation**

Write a bash script named [`createDirectories.sh`](http://createDirectories.sh). When executed with three arguments (directory name, start number, and end number), the script should create a specified number of directories with dynamic names.

### **Question 2: User Account Setup**

Write a separate bash script named [`createUsers.sh`](http://createUsers.sh). This script should create two user accounts (`user1` and `user2`) and display their usernames.

### **Question 3: Automate with Cron Job**

Extend the automation by adding a cronjob to regularly execute the [`createDirectories.sh`](http://createDirectories.sh) script at a specific time.

Write a bash script named [`scheduleDirectoryCreation.sh`](http://scheduleDirectoryCreation.sh). This script should:

1. Accept two arguments - the directory name and the frequency in minutes.
    
2. Create a cronjob that runs the [`createDirectories.sh`](http://createDirectories.sh) script with the specified directory name and a range of numbers.
    

## Question 1:

## Solution

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706695804676/2af5e48a-2b38-491e-a9d8-0c29e4067a16.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706695836209/e4c5f6e0-62b0-4dc4-8c87-33577f67cc7f.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706695861190/b919b257-35a1-48a8-9610-db7a68bdd1b4.png align="center")

### Output:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706695891709/95b8003d-50e9-4b3b-8b16-bf91fc7c24e5.png align="center")

## Question 2:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706696204519/67286b32-fe72-4876-8e45-aced7fd8f612.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706696119620/42f3a224-361d-4c9f-837b-aec9d65741af.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706696224953/0af1d7bb-6372-49ee-bd05-25899cf7cad9.png align="center")

### Output:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706696023107/a0c91bb7-f331-4def-abaa-988a215713ca.png align="center")

To check a user we need to see it in the **<mark>/etc/passwd </mark>** directory.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706696102149/458c958c-551d-4cc4-ba97-c3acb1671b6a.png align="center")

## Question 3 :

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706696284370/2ab61755-604a-4dc0-9890-8d175e5d46af.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706696304944/c5daa938-cb11-433c-a344-8fd871eabf7e.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706696327706/54170c5b-929d-4c3d-8113-8fc14b063967.png align="center")

### Output:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706696356945/7481bdaa-15b0-4901-89b9-49efec34f7f6.png align="center")

## Conclusion:

In summary, we've explored shell scripting, Cron, and user management in Linux. We've learned to schedule tasks, automate processes, and tackled a Bash Script Challenge. By mastering these skills, we're equipped to enhance efficiency in system administration through automation. Let's continue our journey of mastering the power of shell scripting in Linux.

Ending this with a quote,

> "In the world of DevOps, collaboration is the code, automation is the rhythm, and continuous improvement is the melody, orchestrating a symphony of efficiency in software delivery."  

Happy Learning.