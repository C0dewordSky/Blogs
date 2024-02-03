---
title: "Day 6 - File System Hierarchy, File Permissions and Access Control Lists"
seoTitle: "Day 6 - File System Hierarchy, File Permissions and Access Control Lis"
datePublished: Thu Feb 01 2024 09:38:34 GMT+0000 (Coordinated Universal Time)
cuid: cls30xjlh000e0al50ib0ewqg
slug: day-6-file-system-hierarchy-file-permissions-and-access-control-lists
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1706765247516/44f64c77-4ee3-4e98-aa9c-edc47ba21e4a.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1706780274223/82237f6f-0df0-4a6f-a8f9-412de2711f85.png
tags: docker, aws, devops, containers, containerization, 2articles1week, technical-writing-1, linux-for-beginners, devops-articles, file-permission, devops-journey, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge, devopscommunity

---

### Introduction

In this blog we will delve into the files in Linux. As we all know that in Linux everything is represented as a file, so we'll dive deep into it and understand some important concepts of File System Hierarchy, the importance of each file in the tree and understand File Permissions and Access control of a file. At the we'll have some hands on practice to make your concepts even more crisp and clear.

## File System Hierarchy

![](https://tecadmin.net/wp-content/uploads/2022/06/linux-filesystem-hierarchy.png align="center")

* In Linux, everything is represented as a file including a hardware program. The files are stored in a directory and every directory stores their respective files. This in Linux is called the **<mark>File System Hierarchy (FSH)</mark>**.
    
* The root directory is **<mark>"/"</mark>** (forward slash) and it is the base directory.
    

### Understanding the Directories:

* **<mark>"/"</mark>** : This is the root directory or the base directory.
    
* **<mark>"/root"</mark>** : It is the home directory of the root user and it stores information about the root user i.e. super user.
    
* **<mark>"/home"</mark>** : It is the home directory for the Local Users. It stores information about the user like personal information, user information, files, login scripts etc.
    
* **<mark>"/bin"</mark>** : **<mark>User Binaries</mark>** . These directories include executable files or programs for commands that are run on the terminal <mark>for all users</mark>. When you run a command in the terminal, its corresponding executable file is located in the <mark>/bin</mark> directory which helps in executing the command.
    
* **<mark>"/sbin"</mark>** : **<mark>System Binaries</mark>** . It also contains binary executable or programs for <mark>system administrative commands</mark>. These are used for system administration and system maintenance. You need administrative privileges to run these commands. for e.g.: reboot, iptables etc.
    
* **<mark>"/etc"</mark>** : This contains Configuration files of the system, application or the server. It also contains subdirectories essential for proper functioning of the system and application.
    
* **<mark>"/usr"</mark>** : **<mark>Unix System Resources</mark>** or **<mark>User Binaries</mark>** or **<mark>User Programs</mark>**. It is a directory where most of your installed software and resources reside. It helps keep the system files separate from user-installed files, making it easier to manage and maintain the system.
    
* **<mark>"/opt"</mark>** : **<mark>Optional Application</mark>**. This directory is used for installing software from a third party vendor. This helps keep these applications separate from the system's default software and prevents conflicts with system files. The software code is stored in the <mark>/opt </mark> directory and the binary executables are linked to <mark>/bin</mark> directory so that all users can run the software.
    
* **<mark>"/lib"</mark>** : This directory in contains essential library files that are crucial for the operating system and applications to function.
    
* **<mark>"/boot"</mark>** : This directory contains the boot executable files that are essential for secured boot of the system. For example: GRUB's boot loader file and Linux Kernels are stored here.
    
* **<mark>"/var"</mark>** : **<mark>Variable files</mark>**. This directory stores the variable files such as log files. In short the content which grows with time, are stored in <mark>/var</mark> directory. For example: <mark>/var/log, /var/lib, /var/mail</mark> etc.
    
* **<mark>"/mnt"</mark>** : This directory is used to <mark>manually mount</mark> a filesystem or a device temporarily. It is a standard location where external storage devices, such as USB drives, external hard disks, or network shares, can be temporarily mounted.
    
* **<mark>"/media"</mark>** : **<mark>Removable Media Devices</mark>**. This directory is used to <mark>automatically mount removable media devices </mark> temporarily. It is the standard location where removable media devices such as USB drives, external hard disks, CD-ROMs, and other storage devices can be mounted.
    
* **<mark>"/temp"</mark>** : Contains temporary files created by the system and the users. These files get deleted when the system is rebooted.
    

## Basic Symbols

**Some more basic symbols**

| S:NO | **Symbol** | **Explanation** | **Examples** |
| --- | --- | --- | --- |
| 1 | / | The forward slash (/) represents the "root" of the filesystem. (Every directory/file in the Linux filesystem is nested under the root / directory.) / also use for directoty separation and path separation | /  is a root directory |
| /home/user/samle/test.txt |  |  |  |
| 2 | ~ | is equal to the current user's home directlry. E.g: /home/someone/ | cd ~ |
| ls ~ |  |  |  |
| 3 | \* | A symbol which stands for "everything". Let's say you want to remove all the .jpg files from your Downloads folder which have their name starting with the "E" character, then you can use this symbol to represent all the other letters except E. See the example. | rm ~/Downloads/E\*.jpg |
| ls /etc/\*c |  |  |  |
| nano /var/log/nginx/\* |  |  |  |
| 4 | & | Run a command in the background. It will return the PID of the newly running process to you and won't show you the output. | sudo apt update & |
| 5 | && | These symbols written together stand for "and". So if you want to run 2 commands together, you can use it. | sudo apt update && sudo apt upgrade |
| 6 | \\ | Allows you to continue writing commands/Bash syntax in new line. | sudo \\ |
| apt \\ |  |  |  |
| update |  |  |  |
| 7 | .. | In many cases, especially in navigation, the two dots stand for the parent folder. | cd .. |
| 8 | . | In navigation or referring to files/folders, the dot stands for the current folder. | ls . |
| 9 | # | Everything after this symbol in the same line is considered to be a comment, so it won't be processed by the shell. | cd # This commands moves you somewhere. |
| 10 | | |  | This is called "Piping", which is the process of redirecting the output of one command to the input of another command. Very useful and common in Linux/Unix-like systems. |
| 11 | \&gt; | Take the output of a command and redirect it into a file (will overwrite the whole file). | ls ~ &gt; output.txt |
| 12 | &lt; | Read the contents of a file into the input of a command. | grep bash &lt; /etc/profile |
| 13 | \&gt;&gt; | Append a text or a command output into the last line of a file. | echo "First Line" &gt; output.txt |
| echo "See this is the last line" &gt;&gt; output.txt |  |  |  |

## File Permissions

![](https://cdn.linuxfordevices.com/wp-content/uploads/2020/01/ls-file-permission-example.png align="center")

### File type:

The file type is determined by the first character of the permission sequence. These are the symbols and their meaning

| Symbol | Meaning |
| --- | --- |
| \- | Regular file |
| d | Directory |
| c | Character Device |
| b | Block Device |
| s | Local Socket file |
| p | Named Pipe |
| l | Symbolic link |

### File Permission:

The Read, Write and execute have been assigned certain values. These values can be used to In order to set permissions for a given file.

| Permission | Value |
| --- | --- |
| Read (r) | 4 |
| Write (w) | 2 |
| Execute (x) | 1 |

We can use these values to set file permissions. For example suppose we have a file `file.txt` and we have to give all the permissions to that file for the User, Group and Others.

since we have to give all the permission, we will sum up the values i.e. 4+2+1 = 7. So the Value 7 resembles all the permissions are granted.

```bash
chmod 777 file.txt

#Output 
-rwxrwxrwx 1 root root Date Time file.txt
```

Similarly if we need to remove write and execute permission for Group and Others from file.txt, we will subtract their respective values from the total i.e. 7 .  
Read+Write = 2+1 = 3, so we will subtract 3 from the Group and Other section of the file .

```bash
chmod 744 file.txt
 
#Output 
-rwxr--r-- 1 root root Date Time file.txt
```

And similarly we can modify the user permission according to our need.

![](https://i.redd.it/vkxuqbatopk21.png align="center")

Read More about File permission [Click Here](https://www.redhat.com/sysadmin/linux-file-permissions-explained).

## Access Control Lists

Access Control Lists (ACLs) provide a more flexible way of controlling access to files and directories than the traditional Unix file permissions. While standard file permissions (read, write, execute) in Unix are limited to the owner, group, and others, ACLs allow you to define permissions for specific users and groups beyond these basic categories.

### some basic commands:

* "**<mark>chown</mark>**" : This command is used to change the Owner of file. A Owner is the entity that created that files and owns it. This command will help in tweaking the file and changing its Ownership.
    
    ```bash
    chown file.txt
    ```
    
* "**<mark>chgrp</mark>**" : This command is used to change the Group of the file. A Group is a collection of users and it provides a way to assign permissions to multiple users simultaneously. This command helps in modifying/changing the group that owns the file.
    
    ```bash
    chgrp file.txt
    ```
    
* "**<mark>chmod</mark>**" : This command is used to change/modify the file permissions of a file or directory.
    
    ```bash
    chmod 777 file.txt
    ```
    

### ACL commands:

* "**<mark>setfacl</mark>**" : This is used to set ACLs. For e.g. to grant read and write access to a file for a specific user:
    
* ```bash
      setfacl -m u:username:rw file.txt
    ```
    
    `-m` option in `setfacl` stands for "modify," and it is used to modify the ACL of a file or directory by adding or changing ACL entries.
    
    `rw`: Read and Write Permission
    
    `u`: To specify the username
    
* "**<mark>gefacl</mark>**" : This command is used to view access control lists of a file or directory.
    
    ```bash
    getfacl file.txt
    ```
    
* **Removing ACLs:**
    
    * To remove ACLs from a file or directory, you can use the `setfacl` command with the `-b` option:
        
        ```bash
        setfacl -b file.txt
        ```
        

Read More about ACLs, [Click Here](https://www.redhat.com/sysadmin/linux-access-control-lists) .

## Scenario Based Practice

### Scenario:

Scenario: You are a system administrator for a company that hosts sensitive financial data on a Linux server. There are three user accounts: Alice, Bob, and Charlie. The financial data files are stored in a directory called "financials," and you want to ensure proper file permissions and access control lists (ACLs) are set up to maintain security and restrict access appropriately.

1. **Initial Setup:**
    
    * Alice is the owner of the "financials" directory.
        
    * Bob is a member of the "finance" group, and Charlie is not a member of any special group.
        

**Tasks:**

1. **File Permissions:**
    
    * Task 1: Set the appropriate file permissions on the "financials" directory to ensure that only Alice can create, delete, and modify files within it.
        
    * Task 2: Grant read and execute permissions on the "financials" directory to members of the "finance" group without allowing them to modify or delete files.
        
2. **Access Control Lists (ACLs):**
    
    * Task 3: Use ACLs to grant Bob read and write access to a specific file1 and file2 within the "financials" directory without affecting other files.
        
    * Task 4: Use ACLs to ensure that Charlie has no access to any file within the "financials" directory, even if the directory permissions would allow it.
        
3. **Verification and Troubleshooting:**
    
    * Task 5: Check the current file permissions and ACLs for the "financials" directory to ensure they match the desired configuration.
        

### Solution:

**Task 1**:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706778550903/7a15622f-09ff-4ae1-a75d-e309703256db.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706778667994/d3994337-3c0c-41f4-ac77-bfffe3aaf159.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706778705479/d9c082eb-52ee-4437-830c-8f6a9efd63d0.png align="center")

**Task 2:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706778852276/0f3ab41f-5964-45b2-9b60-5de31ea06c5b.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706778891356/6a944b4a-00fd-4128-a5fe-fd1d78390d09.png align="center")

**Task 3:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706779332223/269301e4-c12f-47c2-877e-fdc76902b6c3.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706779447283/09034e92-6118-45eb-b4a9-de021650a042.png align="center")

**Task 4:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706779699672/d26de524-6bdd-4943-90e0-e672abe4916a.png align="center")

**Task 5:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706779753178/42682d10-cce6-4b75-8945-125c0d02e976.png align="center")

**NOTE: In case you get an error while using acl commands, try installing the acl package by your default package installer. For ubuntu users:**`sudo apt install acl` is the command.

## Conclusion

This blog explored Linux file systems, emphasizing the File System Hierarchy, basic symbols, and commands for efficient terminal use. Key points included file permissions using the "chmod" command and an introduction to Access Control Lists (ACLs) for advanced access management. The hands-on practice offered practical application, providing readers with essential knowledge for effective Linux system administration. I hope this adds value to your learnings.

Ending this with a quote

> Failure is simply the opportunity to begin again, this time more intelligently. - Henry Ford

Happy Learning.