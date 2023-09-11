---
title: "Day - 06 Of 90DaysofDevops"
datePublished: Sat Jul 22 2023 17:29:56 GMT+0000 (Coordinated Universal Time)
cuid: clkeacgm1000h09l50u438fdu
slug: day-06-of-90daysofdevops
tags: devops-articles, 90daysofdevops, trainwithshubham, devopscommunity, trainwithshubham-techwithankush-seekhoaursikhao-twscommunitybuilders-90daysofdevops-connections-growth-community-learning-linkedin-devops-awsdevops-awscloud-awscommunity-aws-docker-dockercontainer-dockerhub-kubernetescluster-kubernetesservices-kubernetes-jenkins-ansible-ansibleautomates-linuxsystemadministration-linuxfoundation-linux-git-github-terraform-grafana-prometheus-cicd-cicdpipelines

---

## **Day -06: Are Your Files Secure? The Ultimate Linux File Permissions and Access Control Lists Check Explained!**

### **Introduction**

In the world of Linux systems, file security is of utmost importance. Understanding Linux file permissions and access control lists (ACLs) and implementing proper access control measures can safeguard your data from unauthorized access, accidental deletions, and potential breaches. This blog post provides a comprehensive guide to Linux file permissions, and access control lists, offering insights into their significance, and practical steps to ensure your files remain secure.

### **What are Linux File Permissions?**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690046456442/a0acac97-86cd-4624-b31a-027043ba0a26.png align="center")

Linux file permissions are a set of rules that dictate who can access, modify, and execute files within a Linux system. The permissions are categorized into three groups: the file owner, the group associated with the file, and others. Each group has distinct read, write, and execute permissions, allowing for fine-grained control over file access.

| position | characters | ownership |
| --- | --- | --- |
| 1 | \- | denotes file type |
| 2-4 | rw- | permission for user |
| 5-7 | rw- | permission for group |
| 8-10 | r-- | permission for other |

### **Why File Security Matters on Linux Systems**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690046574172/98f1c813-34e8-4ce0-a946-930bdce5e768.jpeg align="center")

Ensuring file security on Linux is crucial to protect sensitive data and maintaining system integrity. Insecure file permissions can lead to unauthorized access, data leaks, and system vulnerabilities. By comprehending the importance of file security and access control lists, you can take proactive measures to mitigate potential risks.

### **How to Check Linux File Permissions**

a. Using Command Line: The command line provides powerful tools to manage file permissions. The `ls` command, along with the `chmod` and `chown` commands, which allows you to view and modify file permissions efficiently. This section covers the command syntax and examples.

Permission can be changed by giving the sum of the mode. Ex- 777 means the user, group and others have permission to read, write and execute i.e. 7=4+2+1.

* "chown" is used to change the ownership permission of a file or directory.
    
* "chgrp" is used to change the group permission of a file or directory.
    
* "chmod" is used to change the other user's permissions of a file or directory.
    
    <table><tbody><tr><td colspan="1" rowspan="1"><p><strong>Symbolic</strong></p></td><td colspan="1" rowspan="1"><p><strong>Mode</strong></p></td><td colspan="1" rowspan="1"><p><strong>Absolute Mode</strong></p></td></tr><tr><td colspan="1" rowspan="1"><p>r</p></td><td colspan="1" rowspan="1"><p>read</p></td><td colspan="1" rowspan="1"><p>4</p></td></tr><tr><td colspan="1" rowspan="1"><p>w</p></td><td colspan="1" rowspan="1"><p>write</p></td><td colspan="1" rowspan="1"><p>2</p></td></tr><tr><td colspan="1" rowspan="1"><p>x</p></td><td colspan="1" rowspan="1"><p>execute</p></td><td colspan="1" rowspan="1"><p>1</p></td></tr><tr><td colspan="1" rowspan="1"><p>(.)</p></td><td colspan="1" rowspan="1"><p>null</p></td><td colspan="1" rowspan="1"><p>0</p></td></tr></tbody></table>
    

b. Using File Managers: Graphical file managers also offer a user-friendly way to check and adjust file permissions. Learn how to navigate your file manager's interface to access the necessary options and apply changes using access control lists.

### **Best Practices for Securing Files on Linux**

a. **Principle of Least Privilege:** Follow the principle of least privilege by granting users only the minimum required permissions. This practice restricts unnecessary access and reduces the risk of potential security breaches. Utilize access control lists to fine-tune user permissions.

b. **Regularly Update File Permissions:** Review and update file permissions regularly, especially when adding new users or modifying system configurations. Staying vigilant ensures that access rights remain up-to-date and aligned with your security policies.

c. **Secure File** Ownership: Assign appropriate ownership to files and directories. Avoid using overly permissive settings and make use of group ownership to simplify access control. Additionally, implement access control lists to provide custom permissions to specific users or groups.

d. **Using ACLs** (Access Control Lists): Access Control Lists (ACLs) provide an advanced level of control over file permissions. Implement ACLs to define custom access rules for specific users or groups. This section explores the usage of access control lists in detail.

To view and modify ACLs, you can use `getfacl` and `setfacl` commands.

### **Conclusion**

Linux file permissions and access control lists are fundamental aspects of file security. By mastering file access control using both traditional permissions and access control lists, you can confidently manage permissions and protect your files from unauthorized access. Secure your data and maintain the integrity of your Linux system with the insights and techniques shared in this blog post.

I also received comprehensive training in various aspects of DevOps methodologies, including continuous integration, continuous deployment, and infrastructure automation. Stay connected with me for more interesting articles about Cloud and DevOps by following me on hashnode,

LinkedIn ([**linkedin.com/in/vedant-adhe-4683b0192**](http://linkedin.com/in/vedant-adhe-4683b0192)**) and**

**GitHub (**[**github.com/VedantAdhe**](http://github.com/VedantAdhe)**)**

**Connect** [**Vedantadhe19@gmail.com**](mailto:Vedantadhe19@gmail.com)

Thank you for reading! Continue to support us, learn from each other and grow with us.