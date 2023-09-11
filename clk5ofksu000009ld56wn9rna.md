---
title: "Day 2 - Basics Linux Command"
datePublished: Sun Jul 16 2023 16:54:21 GMT+0000 (Coordinated Universal Time)
cuid: clk5ofksu000009ld56wn9rna
slug: day-2-basics-linux-command
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1689526316246/76276a7b-e0a4-496e-9686-8fc7d2e93988.png
tags: devopscommunity, trainwithshubham-techwithankush-seekhoaursikhao-twscommunitybuilders-90daysofdevops-connections-growth-community-learning-linkedin-devops-awsdevops-awscloud-awscommunity-aws-docker-dockercontainer-dockerhub-kubernetescluster-kubernetesservices-kubernetes-jenkins-ansible-ansibleautomates-linuxsystemadministration-linuxfoundation-linux-git-github-terraform-grafana-prometheus-cicd-cicdpipelines

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689522092756/64ffac07-4e49-45a1-9ef3-0805da41f286.png align="center")

1. Introduction
    
2. Basic Linux Commands
    
3. Check your present working directory.
    
4. List all the files or directories including hidden files.
    
5. Create a nested directory A/B/C/D/E
    
6. Conclusion
    

# Introduction

**Linux Introduction** Linux 🐧 is a free and open-source operating system that runs on a wide range of hardware platforms, from personal computers to supercomputers. It was created by Linus Torvalds in 1991 and has since become a popular alternative to proprietary operating systems like Windows and macOS. 🖥️

# Basics Linux command 🕹️

### File System 📂

1. **pwd**: This command stands for "Print Working Directory." It shows you the current directory you are in.
    
2. **ls**: Use the `ls` command to list files and directories in the current directory.
    
3. **cd**: The `cd` command is used to change directories.
    

### Working with Directories 📁

1. **mkdir**: This command is used to create a new directory.
    
2. **rmdir**: The `rmdir` command is used to remove an empty directory.
    
3. **tree**: Display directory structure in a tree-like format.
    

### File Operations 📄

1. **cp**: The `cp` command is used to copy files or directories.
    
2. **mv**: Use the `mv` command to move files or directories.
    
3. **rm**: Use the `rm` command to delete files or directories.
    
4. **touch**: The `touch` command is used to create a new empty file.
    

### Viewing File Content 👀

1. **cat**: The `cat` command is used to display the contents of a file on the terminal.
    
2. **head**: Use the `head` command to display the first few lines of a file.
    
3. **tail**: The `tail` command is used to display the last few lines of a file.
    

# **Task 1** ✔**: Checking Your Present Working Directory**

If you are new to the world of Linux, you might feel a little overwhelmed by the command line interface. But do not worry! In this blog, we'll walk you through one of the most basic, yet important concepts: checking your current working directory.

### **Understanding the Present Working Directory (PWD)**

In Linux, your "current working directory" (PWD) simply refers to the directory (or folder) where you are currently located in the file system. Think of it like your current location on a map. Just as you need to know your location to figure out where you are going, knowing your PWD is critical to navigating the Linux file system efficiently.

The "pwd" command: your localization tool

To check your current working directory, use the "pwd" command. The abbreviation stands for "print working directory" and is something like your personal search tool, telling you exactly where you are in the Linux file system.

# Why it is important to know your PWD

Knowing your current working directory may seem like a small detail, but it plays an important role in navigating the Linux system and executing commands effectively. Here's why it's important:

1. Navigation: if you want to change to another directory, you need to know where you are. The pwd command helps you find out where you are so you can decide where to go next.
    
2. Reference: Some commands and scripts require you to specify a full path or a relative path to a file or directory. If you know you can accurately reference other locations.
    
3. Troubleshooting: When you encounter problems or errors in the terminal, knowing your "pwd" can help you and others better understand the context, making troubleshooting easier.
    

# Task 2:List all the files or directories including hidden files.

Understand the command " ls" with the option "-a":

The ls command is used to list files and directories in a directory. By default, it displays only the visible files and directories and omits those that begin with a period (hidden files). However, if you add the -a option to the ls command, hidden files are also listed.

To list all files and directories, including hidden files, in the current directory under Linux, you can use the "ls" command with the "-a" option.

Example: ls -a

## **Task 3 📂: Create a nested directory A/B/C/D/E**

Have you ever gotten lost in a maze of files and folders, desperately searching for a way to organize your data efficiently? Have no fear! In this blog, we'll show you how to create a nested A/B/C/D/E directory structure in the Linux command line interface that will allow you to tame the chaos and keep a well-organized file system.

### Understanding nested directories

Before we dive into the creation process, we should understand what a nested directory structure is. Simply put, it means that there are directories within directories that form a tree-like structure. Each directory can contain files as well as additional subdirectories. This hierarchical arrangement helps keep related data together so that you can manage and find your files more easily.

1. Step 1: Open the terminal
    

To get started, open the terminal on your Linux system. You can usually find it in the Applications menu or use the key combination Ctrl + Alt + T.

1. Step: Navigate to the desired location
    

Before we create the nested directories, make sure you are in the location where you want to create the directories. You can use the cd command to navigate to the desired location. For example, if you want to create nested directories in your home directory, simply type:

cd ~

1. Step: Create the nested directories
    

Now comes the exciting part! To create the A/B/C/D/E nested directory structure, use the mkdir command with the -p option. The -p option ensures that the entire nested structure is created, even if the parent directories do not yet exist. Type the following command and press Enter:

mkdir -p A/B/C/D/E

1. Step: Check the creation
    
    To verify that the nested directories were created successfully, use the ls command to list the contents of the parent directory. Type:
    
    ls A/B/C/D/E
    

# Conclusion ▶️

Creating a nested directory A/B/C/D/E is a simple but effective way to bring order to the chaos of your file system. With just a few commands in the Linux terminal, you can build a well-organized and efficient structure that will make your computer life much smoother.

Stay connected with me for more interesting articles about Cloud and DevOps by following me on hashcode, LinkedIn ([**https://www.linkedin.com/in/vedant-adhe-4683b0192/**](https://www.linkedin.com/in/vedant-adhe-4683b0192/)) and GitHub ([**https://github.com/VedantAdhe**](https://github.com/VedantAdhe))

Thank you for reading! Continue to support us, learn from each other and grow with us.