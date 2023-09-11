---
title: "Day-12  of 90Day's of  DevOps"
datePublished: Fri Aug 04 2023 16:07:20 GMT+0000 (Coordinated Universal Time)
cuid: clkws4ami000909jz10qyb9jm
slug: day-12-of-90days-of-devops
tags: tws, devopscommunity, trainwithshubham-techwithankush-seekhoaursikhao-twscommunitybuilders-90daysofdevops-connections-growth-community-learning-linkedin-devops-awsdevops-awscloud-awscommunity-aws-docker-dockercontainer-dockerhub-kubernetescluster-kubernetesservices-kubernetes-jenkins-ansible-ansibleautomates-linuxsystemadministration-linuxfoundation-linux-git-github-terraform-grafana-prometheus-cicd-cicdpipelines

---

* Introduction
    
* Basic Linux commands
    
* File Permission commands
    
* Environment Variables command
    
* User management commands of Linux
    
* Networking commands
    
* Process commands
    

## GIT CHEAT SHEET

Git is the free open-source distributed version control system that's responsible for everything GitHub-related that happens locally on your computer. This cheat sheet features the most important and commonly used Git commands for easy reference.

* ## INSTALLATION & GUIS
    

With platform-specific installers for Git, GitHub also provides the ease of staying up-to-date with the latest releases of the command line tool while providing a graphical user interface for day-to-day interaction, review, and repository synchronization.

* ## GitHub for Windows
    

[https://windows.github.com](https://windows.github.com)

* ## GitHub for Mac
    

[https://mac.github.com](https://mac.github.com)

For Linux and Solaris platforms, the latest release is available on the oﬃcial Git web site.

* ## Git for All Platforms
    

[http://git-scm.com](http://git-scm.com)

## **Networking commands :**

<table><tbody><tr><td colspan="1" rowspan="1"><p><strong>Command</strong></p></td><td colspan="1" rowspan="1"><p><strong>Description</strong></p></td><td colspan="1" rowspan="1"><p></p></td></tr><tr><td colspan="1" rowspan="1"><p>SSH username@ip-address or hostname</p></td><td colspan="1" rowspan="1"><p>login into a remote Linux machine using SSH</p></td><td colspan="1" rowspan="1"><p></p></td></tr><tr><td colspan="1" rowspan="1"><p>Ping hostname="" or =""</p></td><td colspan="1" rowspan="1"><p>To ping and Analyze network and host connections</p></td><td colspan="1" rowspan="1"><p></p></td></tr><tr><td colspan="1" rowspan="1"><p>dir</p></td><td colspan="1" rowspan="1"><p>Display files in the current directory of a remote computer</p></td><td colspan="1" rowspan="1"><p></p></td></tr><tr><td colspan="1" rowspan="1"><p>cd "dirname"</p></td><td colspan="1" rowspan="1"><p>change the directory to “dirname” on a remote computer</p></td><td colspan="1" rowspan="1"><p></p></td></tr><tr><td colspan="1" rowspan="1"><p>put file</p></td><td colspan="1" rowspan="1"><p>upload ‘file’ from local to remote computer</p></td><td colspan="1" rowspan="1"><p></p></td></tr><tr><td colspan="1" rowspan="1"><p>get file</p></td><td colspan="1" rowspan="1"><p>Download the ‘file’ from the remote to the local computer</p></td><td colspan="1" rowspan="1"><p></p></td></tr><tr><td colspan="1" rowspan="1"><p>quit</p></td><td colspan="1" rowspan="1"><p>Logout</p></td><td colspan="1" rowspan="1"><p></p></td></tr></tbody></table>

# **Basic Linux commands :**

<table><tbody><tr><td colspan="1" rowspan="1"><p><strong>Commands</strong></p></td><td colspan="1" rowspan="1"><p><strong>Description</strong></p></td></tr><tr><td colspan="1" rowspan="1"><p>ls</p></td><td colspan="1" rowspan="1"><p>Lists all files and directories in the present working directory</p></td></tr><tr><td colspan="1" rowspan="1"><p>ls -R</p></td><td colspan="1" rowspan="1"><p>Lists files in sub-directories as well</p></td></tr><tr><td colspan="1" rowspan="1"><p>ls -a</p></td><td colspan="1" rowspan="1"><p>Lists hidden files as well</p></td></tr><tr><td colspan="1" rowspan="1"><p>ls -al</p></td><td colspan="1" rowspan="1"><p>Lists files and directories with detailed information like permissions, size, owner, etc.</p></td></tr><tr><td colspan="1" rowspan="1"><p>cd ~</p></td><td colspan="1" rowspan="1"><p>Navigate to the HOME directory</p></td></tr><tr><td colspan="1" rowspan="1"><p>cd . .</p></td><td colspan="1" rowspan="1"><p>Move one level up</p></td></tr><tr><td colspan="1" rowspan="1"><p>cd</p></td><td colspan="1" rowspan="1"><p>To change to a particular directory</p></td></tr><tr><td colspan="1" rowspan="1"><p>cd /</p></td><td colspan="1" rowspan="1"><p>Move to the root directory</p></td></tr><tr><td colspan="1" rowspan="1"><p>cat &gt; filename</p></td><td colspan="1" rowspan="1"><p>Creates a new file</p></td></tr><tr><td colspan="1" rowspan="1"><p>cat filename</p></td><td colspan="1" rowspan="1"><p>Displays the file content</p></td></tr><tr><td colspan="1" rowspan="1"><p>cat file1 file2 &gt; file3</p></td><td colspan="1" rowspan="1"><p>Joins two files (file1, file2) and stores the output in a new file (file3)</p></td></tr><tr><td colspan="1" rowspan="1"><p>mv file "new file path"</p></td><td colspan="1" rowspan="1"><p>Moves the files to the new location</p></td></tr><tr><td colspan="1" rowspan="1"><p>mv filename new_file_name</p></td><td colspan="1" rowspan="1"><p>Renames the file to a new filename</p></td></tr><tr><td colspan="1" rowspan="1"><p>sudo</p></td><td colspan="1" rowspan="1"><p>Allows regular users to run programs with the security privileges of the superuser or root</p></td></tr><tr><td colspan="1" rowspan="1"><p>rm filename</p></td><td colspan="1" rowspan="1"><p>Deletes a file</p></td></tr><tr><td colspan="1" rowspan="1"><p>man</p></td><td colspan="1" rowspan="1"><p>Gives help information on a command</p></td></tr><tr><td colspan="1" rowspan="1"><p>history</p></td><td colspan="1" rowspan="1"><p>Gives a list of all past commands typed in the current terminal session</p></td></tr><tr><td colspan="1" rowspan="1"><p>clear</p></td><td colspan="1" rowspan="1"><p>Clears the terminal</p></td></tr><tr><td colspan="1" rowspan="1"><p>mkdir directory-name</p></td><td colspan="1" rowspan="1"><p>Creates a new directory in the present working directory or an at the specified path</p></td></tr><tr><td colspan="1" rowspan="1"><p>rmdir</p></td><td colspan="1" rowspan="1"><p>Deletes a directory</p></td></tr><tr><td colspan="1" rowspan="1"><p>mv</p></td><td colspan="1" rowspan="1"><p>Renames a directory</p></td></tr><tr><td colspan="1" rowspan="1"><p>apt-get</p></td><td colspan="1" rowspan="1"><p>The command used to install and update packages</p></td></tr></tbody></table>

## **File Permission commands :**

<table><tbody><tr><td colspan="1" rowspan="1"><p><strong>Command</strong></p></td><td colspan="1" rowspan="1"><p><strong>Description</strong></p></td></tr><tr><td colspan="1" rowspan="1"><p>ls -l</p></td><td colspan="1" rowspan="1"><p>to show file type and access permission</p></td></tr><tr><td colspan="1" rowspan="1"><p>r</p></td><td colspan="1" rowspan="1"><p>read permission</p></td></tr><tr><td colspan="1" rowspan="1"><p>w</p></td><td colspan="1" rowspan="1"><p>write permission</p></td></tr><tr><td colspan="1" rowspan="1"><p>x</p></td><td colspan="1" rowspan="1"><p>execute permission</p></td></tr><tr><td colspan="1" rowspan="1"><p>-=</p></td><td colspan="1" rowspan="1"><p>no permission</p></td></tr><tr><td colspan="1" rowspan="1"><p>Chown user</p></td><td colspan="1" rowspan="1"><p>For changing the ownership of a file/directory</p></td></tr><tr><td colspan="1" rowspan="1"><p>Chown user: group filename</p></td><td colspan="1" rowspan="1"><p>change the user as well as a group for a file or directory</p></td></tr></tbody></table>

## **Environment Variables command :**

<table><tbody><tr><td colspan="1" rowspan="1"><p><strong>Command</strong></p></td><td colspan="1" rowspan="1"><p><strong>Description</strong></p></td></tr><tr><td colspan="1" rowspan="1"><p>echo $VARIABLE</p></td><td colspan="1" rowspan="1"><p>To display the value of a variable</p></td></tr><tr><td colspan="1" rowspan="1"><p>env</p></td><td colspan="1" rowspan="1"><p>Displays all environment variables</p></td></tr><tr><td colspan="1" rowspan="1"><p>VARIABLE_NAME=variable_value</p></td><td colspan="1" rowspan="1"><p>Create a new variable</p></td></tr><tr><td colspan="1" rowspan="1"><p>Unset</p></td><td colspan="1" rowspan="1"><p>Remove a variable</p></td></tr><tr><td colspan="1" rowspan="1"><p>export Variable=value</p></td><td colspan="1" rowspan="1"><p>To set the value of an environment variable</p></td></tr></tbody></table>

## **User management commands of Linux :**

<table><tbody><tr><td colspan="1" rowspan="1"><p><strong>Command</strong></p></td><td colspan="1" rowspan="1"><p><strong>Description</strong></p></td></tr><tr><td colspan="1" rowspan="1"><p>sudo adduser username</p></td><td colspan="1" rowspan="1"><p>To add a new user</p></td></tr><tr><td colspan="1" rowspan="1"><p>sudo passwd -l 'username'</p></td><td colspan="1" rowspan="1"><p>To change the password of a user</p></td></tr><tr><td colspan="1" rowspan="1"><p>sudo userdel -r 'username'</p></td><td colspan="1" rowspan="1"><p>To remove a newly created user</p></td></tr><tr><td colspan="1" rowspan="1"><p>sudo usermod -a -G GROUPNAME USERNAME</p></td><td colspan="1" rowspan="1"><p>To add a user to a group</p></td></tr><tr><td colspan="1" rowspan="1"><p>sudo deluser USER GROUP NAME</p></td><td colspan="1" rowspan="1"><p>To remove a user from a group</p></td></tr><tr><td colspan="1" rowspan="1"><p>finger</p></td><td colspan="1" rowspan="1"><p>Shows information of all the users logged in</p></td></tr><tr><td colspan="1" rowspan="1"><p>finger username</p></td><td colspan="1" rowspan="1"><p>Gives information about a particular user</p></td></tr></tbody></table>

## **Process commands :**

<table><tbody><tr><td colspan="1" rowspan="1"><p><strong>Command</strong></p></td><td colspan="1" rowspan="1"><p><strong>Description</strong></p></td><td colspan="1" rowspan="1"><p></p></td></tr><tr><td colspan="1" rowspan="1"><p>bg</p></td><td colspan="1" rowspan="1"><p>To send a process to the background</p></td><td colspan="1" rowspan="1"><p></p></td></tr><tr><td colspan="1" rowspan="1"><p>fg</p></td><td colspan="1" rowspan="1"><p>To run a stopped process in the foreground</p></td><td colspan="1" rowspan="1"><p></p></td></tr><tr><td colspan="1" rowspan="1"><p>top</p></td><td colspan="1" rowspan="1"><p>Details on all Active Processes</p></td><td colspan="1" rowspan="1"><p></p></td></tr><tr><td colspan="1" rowspan="1"><p>ps</p></td><td colspan="1" rowspan="1"><p>Give the status of processes running for a user</p></td><td colspan="1" rowspan="1"><p></p></td></tr><tr><td colspan="1" rowspan="1"><p>ps PID</p></td><td colspan="1" rowspan="1"><p>Gives the status of a particular process</p></td><td colspan="1" rowspan="1"><p></p></td></tr><tr><td colspan="1" rowspan="1"><p>pidof</p></td><td colspan="1" rowspan="1"><p>Gives the Process ID (PID) of a process</p></td><td colspan="1" rowspan="1"><p></p></td></tr><tr><td colspan="1" rowspan="1"><p>kill PID</p></td><td colspan="1" rowspan="1"><p>Kills a process</p></td><td colspan="1" rowspan="1"><p></p></td></tr><tr><td colspan="1" rowspan="1"><p>nice</p></td><td colspan="1" rowspan="1"><p>Starts a process with a given priority</p></td><td colspan="1" rowspan="1"><p></p></td></tr><tr><td colspan="1" rowspan="1"><p>renice</p></td><td colspan="1" rowspan="1"><p>Changes the priority of an already running process</p></td><td colspan="1" rowspan="1"><p></p></td></tr><tr><td colspan="1" rowspan="1"><p>df</p></td><td colspan="1" rowspan="1"><p>Gives free hard disk space on your system</p></td><td colspan="1" rowspan="1"><p></p></td></tr><tr><td colspan="1" rowspan="1"><p>free</p></td><td colspan="1" rowspan="1"><p>Gives free RAM on your system</p></td><td colspan="1" rowspan="1"><p></p></td></tr></tbody></table>

### **Conclusion**

Thank you for reading!In summary, the Git Cheat Sheet serves as a valuable quick reference guide for both beginners and experienced developers using Git. It summarizes the most important Git commands and concepts in a clear and accessible format, making it easier to manage version control and collaborate effectively on projects. With the help of this cheat sheet, developers can streamline their workflows, avoid common mistakes, and gain a deeper understanding of Git's features. By leveraging the power of Git, individuals and teams can work more efficiently and ensure better code management and version control. Whether it's creating branches, merging changes, resolving conflicts, or working with remote repositories, the Git Cheat Sheet is an indispensable companion to mastering the complexities of version control. With continued practice and experience, developers can realize the full potential of Git and become even more proficient in software development. Have fun programming!

LinkedIn ([**linkedin.com/in/vedant-adhe-4683b0192**](http://linkedin.com/in/vedant-adhe-4683b0192)**) and**

**GitHub (**[**github.com/VedantAdhe**](http://github.com/VedantAdhe)**)**

**Connect** [**Vedantadhe19@gmail.com**](mailto:Vedantadhe19@gmail.com)