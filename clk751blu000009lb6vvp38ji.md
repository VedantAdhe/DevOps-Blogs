---
title: "Day-3 Basic Linux Commands"
datePublished: Mon Jul 17 2023 17:26:55 GMT+0000 (Coordinated Universal Time)
cuid: clk751blu000009lb6vvp38ji
slug: day-3-basic-linux-commands
tags: devops, 90daysofdevops, trainwithshubham, tws, trainwithshubham-techwithankush-seekhoaursikhao-twscommunitybuilders-90daysofdevops-connections-growth-community-learning-linkedin-devops-awsdevops-awscloud-awscommunity-aws-docker-dockercontainer-dockerhub-kubernetescluster-kubernetesservices-kubernetes-jenkins-ansible-ansibleautomates-linuxsystemadministration-linuxfoundation-linux-git-github-terraform-grafana-prometheus-cicd-cicdpipelines

---

# Introduction

Linux, the open-source operating system, has become an integral part of the technology world because of its versatility, security and flexibility. Whether you are an aspiring developer, system administrator, or everyday user, understanding basic Linux commands is critical to getting up to speed and harnessing the full power of this powerful platform. In this blog, we'll look at some basic Linux commands that will lay the foundation for your journey into the world of Linux.

## Mostly Used Commands in DevOps 📝

1. pwd - print working directory This command displays the current directory path you are working in.
    
2. ls - list files and directories Used to list the files and directories within the current directory. Add options like -l for detailed information and -a to show hidden files.
    
3. cd - change directory Use this command to switch between directories. Use cd to go to a specific directory or cd .. to go up one level.
    
4. touch - Create empty files Create new empty files with the touch command followed by the desired file name(s).
    
5. mkdir - create directories To create a new directory, simply type mkdir. You can create nested directories with the -p option.
    
6. rm - delete files and directories The rm command allows you to delete files and directories. Be careful when using this command because it does not move files to the trash; they are permanently deleted.
    
7. cp - copy files and directories Copy files or directories with the cp command, followed by the source and destination paths.
    
8. mv - move and rename files and directories Move files or directories to a new location or rename them with the mv command.
    
9. cat - concatenate and display files Display the contents of a file with cat. It is also used to concatenate and combine multiple files.
    
10. Nano (or vim or emacs) - text editors Linux offers several text editors. Nano is beginner friendly, while Vim and Emacs offer more advanced features.
    
11. head and tail - show the beginning and end of files Display the first lines of a file with a head or the last lines with a tail.
    
12. less - paginate through files Display files one page at a time with the less command so that you can browse, search, and navigate conveniently.
    
13. ps - show processes List all running processes with ps and use options like aux to get more detailed information.
    
14. kill - terminate processes Terminate a running process with the kill command followed by the process number ID (PID).
    

# Task 1 : To view what's written in a file ✍🏼

\-&gt; You can use the `cat` command to view the content of a text file. Open the Terminal, navigate to the directory where the file is located, and then run:

```bash
cat filename.txt
```

# Task 2: To change the access permissions of files.

**Chmod:** This command is used to change the access permissions of files and directories.

1. Grant read and write permissions to the owner of the file and remove all permissions for others, you can use
    

```bash
chmod u+rw filename
```

1. This command adds read and write permissions for the owner and removes all permissions for the group and others
    

```bash
chmod go-rwx filename
```

# Task 3 : **To check which commands you have run till now 📜**

The command history is usually managed by the Bash shell which is the default shell for many distributions. To view the command history, you can use the `history` command in the terminal:

```bash
history
```

# Task 4: To remove a directory/ Folder

1. The `rmdir` command is used to remove an empty directory. If the directory contains any files or subdirectories, `rmdir` will not work and will show an error.
    

```bash
rmdir directory_name
```

1. The `rm` command can be used to remove both files and directories, including non-empty directories. When using `rm` with directories, you need to add the `-r` (recursive) option to remove the directory and its contents.
    

```bash
rm -r directory_name
```

# 5 Task: To create a fruits.txt file and to view the content.

To create a "fruits.txt" file in Linux, you can use the "**touch**" command.

This command creates an empty file named "fruits.txt" in the current directory.

Examps :

```bash
cat fruits.txt
```

# 6 Task: Add content in devops.txt (One in each line) - Apple, Mango, Banana, Cherry, Kiwi, Orange, Guava.

To add the contents of the "devops.txt" file on Linux, you can use a text editor such as Nano or vim, or simply use the echo command to append each item to the file, one per line. Here are the steps to use the echo command:

```bash
echo -e "Apple\nMango\nBanana\nCherry\nKiwi\nOrange\nGuava" > devops.txt
```

This command overwrites the existing contents of "devops.txt" if it already exists, or creates a new file if it does not.

```bash
Apple
Mango
Banana
Cherry
Kiwi
Orange
Guava
```

Each item is on a separate line.

# 7 Task: To Show only the top three fruits from the file.

You can use the combination of `sort`, `head`, and `uniq` commands. Assuming the file contains a list of fruits, one fruit per line, here's how you can achieve it:

Let's assume the file is named "fruits.txt". Open a terminal and follow these steps:

1. Sort the file in alphabetical order:
    

```bash
sort fruits.txt
```

1. Count the occurrences of each fruit and display them in descending order:
    

```bash
sort fruits.txt | uniq -c | sort -nr
```

1. Show only the top three fruits using `head`:
    

```bash
sort fruits.txt | uniq -c | sort -nr | head -n 3
```

# 8 Task: To Show only the bottom three fruits from the file.

To display only the bottom three fruits from a file using Linux, you can use a combination of the `tail` and `head` commands. The `tail` command is used to display the last few lines of a file, and the `head` command can be used to display the first few lines of a file. By combining these two commands, we can show only the bottom three lines (fruits) of the file.

Assuming the file containing the fruits is named `fruits.txt`, you can use the following command in the terminal:

```bash
tail -n 3 fruits.txt
```

# 9 Task: To create another file Colors.txt and to view the content.

To create a new file called "Colours.txt" on Linux, you can use the command "touch" followed by the desired file name. This command creates an empty file named "Colours.txt" in the current directory. To display the contents of the file, you can now use the "cat" command:

```bash
touch Colors.txt
cat Colors.txt
```

# 10 Task: Add content in Colors.txt (One in each line) - Red, Pink, White, Black, Blue, Orange, Purple, Grey

Using `echo` command:

```bash
echo "Red" > Colors.txt
echo "Pink" >> Colors.txt
echo "White" >> Colors.txt
echo "Black" >> Colors.txt
echo "Blue" >> Colors.txt
echo "Orange" >> Colors.txt
echo "Purple" >> Colors.txt
echo "Grey" >> Colors.txt
```

The first echo command creates the file "Colors.txt" and adds the word "Red" to it. Subsequent echo commands add each color to the file on a new line, using the redirection operator

```bash
Red
Pink
White
Black
Blue
Orange
Purple
Grey
```

# 11 Task: To find the difference between fruits.txt and Colors.txt file.

To find the difference between two text files in Linux, you can use the `diff` command. Here's how you can compare the `fruits.txt` and `Colors.txt` files:

```bash
diff fruits.txt Colors.txt
```

The `diff` command will output the differences between the two files, if any. If the files are identical, it won't display anything. If there are differences, it will show the lines that differ in both files.

If the files have many differences or are large, it can be helpful to use some options to control the output.

1. To see a side-by-side comparison, you can use the `-y` option:
    
    ```bash
    diff -y fruits.txt Colors.txt  
    ```
    

1. To see a context-based comparison, you can use the `-c` option:
    

```bash
diff -c fruits.txt Colors.txt
```

1. To generate a unified diff, you can use the `-u` option:
    

```bash
diff -u fruits.txt Colors.txt
```