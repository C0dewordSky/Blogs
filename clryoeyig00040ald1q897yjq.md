---
title: "Day 3 - Basic Linux Commands"
seoTitle: "Day 3 - Basic Linux Commands"
datePublished: Mon Jan 29 2024 08:37:07 GMT+0000 (Coordinated Universal Time)
cuid: clryoeyig00040ald1q897yjq
slug: day-3-basic-linux-commands
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/jG8nlwLRZTM/upload/1373191794359b4d9758d6eebad18c13.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1706517396202/fcb7b262-b174-4a66-adc2-24c3f1e24d40.png
tags: linux, learning, hashnode, 2articles1week, viral, linux-basics, linux-commands, 90daysofdevops, 90daysofdevopschallenge

---

![](https://www.redhat.com/sysadmin/sites/default/files/styles/full/public/2021-11/linux-command-line-ls-output_1000x600.jpg?itok=9APn6NKY align="center")

In this blog we will be learning and understanding some basic Linux Commands using suitable examples.

### Commands:

* **To View what's written in a file:**
    
    For this we use the ***<mark>cat</mark>*** command. What it basically does is, it enters the file and print its content on the terminal.
    
    ```bash
    cat <file_name>
    ```
    
* **To change the access permissions of files.**
    
    File Permissions are permissions granted to a file in the order of Read(r), Write(w) and Execute(x). These permissions are granted to the Owners(u), Groups(g) and Others(o) respectively. Only those who have the appropriate permissions can perform tasks like read, write delete etc.
    
    ![](https://miro.medium.com/v2/resize:fit:640/format:webp/0*WYBjoZCBXGcbI-gD.jpg align="center")
    
    In the image above we can see that the user has *<mark>all </mark>* the permissions, the group has *<mark>only read and write</mark>* permission and others i.e. other users have *<mark>only read </mark>* permission that means they cannot write or execute any action with the file.
    

The Command for changing file permission is ***<mark>chmod </mark>*** i.e. **<mark>ch</mark>**ange **<mark>mod</mark>**e

```bash
chmod rwxrw-r-- <file_name>
```

Note: Only the current owner or Super User can change file permissions. For other user to change the permission.

There are other variations of File Permissions in Linux which we will cover in depth on Day 6.

* **To remove a directory/ Folder.**
    
    To remove any file and folder in linux, the command used is ***<mark>rm</mark>*** i.e. **<mark>R</mark>**e**<mark>m</mark>**ove, followed by the file or folder name.
    
    ```bash
    rm <file_name>
    ```
    
    But there's a catch when we move forward to delete a directory/folder. The folder may contain some files, so using simply ***<mark>rm</mark>*** <mark>will not work</mark>. We have to remove the files as well that's inside the folder, so we need to use the ***<mark>-r</mark>*** flag along with ***<mark>rm</mark>*** command.
    
    The ***<mark>-r flag</mark>*** stands for Recursive i.e. in simple words it will delete the files first and then the folder.
    
    ```bash
    rm -r <folder_name>
    ```
    
* **To check which commands you have run till now.**
    

To check the history of commands that have been run on the the terminal, we type ***<mark>history</mark>*** and press enter. This will print all the commands that have been run on the screen.

```bash
history 
```

* **To add Content in a file:**
    
    To add any content or edit a file we use ***<mark>vim editor</mark>***. This editor helps us in editing the file inside the terminal.
    
    ```bash
    vim <file_name>
    ```
    
    Once we enter the file, we can edit it as per our need. Press " ***<mark> i </mark>*** " as you enter the editor to enable editing mode or **interactive mode**.
    
    **Note**: To exit the vim editor while saving your changes/edits, **<mark>press esc</mark>** first and then write **<mark>:wq </mark>** and press enter.
    
* **To View top or bottom few lines of a file:**
    

To view the top few lines use the ***<mark>head </mark>*** command, followed by the number of lines you want to see and the name of the file.

To view the bottom few lines use the ***<mark>tail</mark>*** command.

```bash
head <file_name> -n n
tail <file_name> -n n
```

<mark>n: any integer</mark>

<mark>-n: flag used for taking input of the number</mark>

## Scenario based Practice:

### Scenario:

You find yourself in a virtual command-line environment, eager to embark on a coding adventure. First, you decide to create a file named `fruits.txt` to store your favorite fruits. How would you go about creating this file and adding the following fruits, each on a new line: Apple, Mango, Banana, Cherry, Kiwi, Orange, and Guava?

With your fruit list in place, you now want to explore some interactive operations. How would you view the content of `fruits.txt` to confirm that your fruits are all there? Once satisfied, how would you narrow down your favorite fruits to display only the top three?

Curiosity strikes, and you wonder about the bottom three fruits. How would you go about showing only the bottom three fruits from the `fruits.txt` file?

But the coding journey doesn't end there. Now, shift your focus to colors. How would you create a new file called `Colors.txt` and add the following colors, each on a separate line: Red, Pink, White, Black, Blue, Orange, Purple, and Grey?

Feeling up for a challenge, how would you find the difference between the contents of `fruits.txt` and `Colors.txt` files?

Now I want you to solve it by yourself and check the answers later below.

1. Creating a <mark>fruits.txt</mark> file
    
    ```bash
    touch fruits.txt
    ```
    
    1. Adding each of the fruits on a new line.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706516619791/d0db5d1e-944e-4a7c-9bea-6e48e287ed65.png align="center")
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706516669136/b758d451-e00a-41e3-9e93-3d82b174d980.png align="center")
        
        1. Showing only top three fruits from the file.
            
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706516740200/597df158-7573-4a54-9de3-b7c8c36445e0.png align="center")
        
    
    1. Showing only bottom three fruits from the file.
        
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706516785789/61141a23-b1d8-4616-8510-4f81001687e5.png align="center")
    
    1. Creating another file Colors.txt .
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706516866013/b740467e-ddd0-4aef-8dcc-41f79ca80161.png align="center")
        
        1. Adding content in Colors.txt (One in each line) - Red, Pink, White, Black, Blue, Orange, Purple, Grey.
            
            ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706516902999/f3ebc3cd-3895-485e-9383-4f2e417b6534.png align="center")
            
            1. Finding the difference between fruits.txt and Colors.txt file
                
                ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706516945656/35d8c499-0baa-4ebc-aa21-e26e680a39e5.png align="center")
                
                NOTE: This is only showing the differences in both the file. If you notice "**<mark>Orange</mark>**" was similar in both the files, so there's no Orange printed on the screen.
                

That's it for this blog and I hope this added value to your learnings. Ending this with a quote by Linus Torvalds:

> That's what makes Linux so good: you put in something, and that effort multiplies. It's a positive feedback cycle.

Happy Learning.