---
title: "Day-23 : Jenkins Freestyle Project for 
                                              DevOps Engineers"
datePublished: Sat Dec 02 2023 07:59:42 GMT+0000 (Coordinated Universal Time)
cuid: clpnrjf8z000k08la078h6g2t
slug: day-23-jenkins-freestyle-project-for-devops-engineers
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1701503934483/5f748175-9f75-4969-b85c-d130ad0cbdd8.jpeg
tags: devops-articles, devops-journey, trainwithshubham-techwithankush-seekhoaursikhao-twscommunitybuilders-90daysofdevops-connections-growth-community-learning-linkedin-devops-awsdevops-awscloud-awscommunity-aws-docker-dockercontainer-dockerhub-kubernetescluster-kubernetesservices-kubernetes-jenkins-ansible-ansibleautomates-linuxsystemadministration-linuxfoundation-linux-git-github-terraform-grafana-prometheus-cicd-cicdpipelines

---

In the previous blog, I explained what CI/CD is. Here’s the link to my blog: [**CI/CD**](https://muditm12.hashnode.dev/day-22-getting-started-with-jenkins#heading-1-cicd). If you haven’t already installed Jenkins on your server, here are the steps to **Install Jenkins on your system**.

### **1\. 🏗️ What is a Build Job?**

A build job in Jenkins is a repeatable process that automates the building, testing, and deploying of software. It is a collection of steps that are executed in a specific order to create a finished product. Jenkins build jobs can be configured to run on a schedule, or they can be manually triggered.

Many different types of build jobs can be created in Jenkins, including:

* Freestyle projects: These are the most basic type of build job, and they allow you to define the steps that are executed in the build process.
    
* Pipelines: Pipelines are a more advanced type of build job that allows you to define the steps in the build process using a declarative syntax.
    
* Multi-configuration projects: These allow you to create multiple builds of the same project, each with different configurations.
    
* Folders: Folders can be used to organize your build jobs.
    
* Multibranch pipelines: These allow you to create pipelines that are based on branches in a Git repository.
    
* Organization folders: These allow you to organize your build jobs by organization.
    

In this blog, I am going to do a Freestyle Project. Let’s learn what a freestyle project is.

### **2\. 🎨 What are Freestyle Projects?**

Freestyle Projects refer to a type of project configuration in Jenkins, a popular automation server. It allows users to create customized and flexible build processes using a graphical interface, offering versatility and control over the build steps and configurations.

---

### **3\. 📝 Tasks**

### **3.1. ✅ Task 1**

1. Create a new Jenkins freestyle project named ToDoApp.
    
2. Configure the project. In the Source Code Management section &gt; Select Git &gt; Enter the GitHub Repository Link and the branch name.
    
3. Repo link I have used: [**Django Todo App**](https://github.com/joy00900/django-todo-cicd).
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701503136161/eb33fab6-ebcc-4c96-a0b1-8e5ce29aabe6.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701503153913/9f33b826-aa1a-41a3-a6bf-d680e6692527.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701503178812/24d51ea6-9c3b-4a4e-bddc-dd70bd03ba10.png align="center")

1. In the Build Steps section &gt; Select Add Build Steps &gt; Select Execute Shell &gt; And type the commands required for your activity.
    

```abap
  docker build -t todoapp .
  docker run -d --name django-todo-app -p 8000:8000 todoapp:latest
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701503263443/4c211d9a-39a9-4416-8e68-77e53365a923.jpeg align="center")

1. Click on Save and Build your project.
    
2. Once the project is built successfully, a green tick can be observed beside the build number.
    
3. We can see the console output and steps of the activity.
    
4. In the final line of the Console Output, we can observe that Finished: Success is printed. That means our build is successful.
    
    I have verified that the ToDo list application is accessible on host\_IP:8000.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701503432004/038b7ca6-68ef-4669-95e1-0095f093ed64.jpeg align="center")

---

### **3.2. ✅ Task 2**

In task 2, we need to create a Jenkins project to run the "docker-compose up -d" command to start the multiple containers defined in the compose file. Set up a cleanup step in the Jenkins project to run the "docker-compose down" command to stop and remove the containers defined in the compose file.

So in the Add build steps of the configuration section, write in the following command and go ahead and build the project.

```abap
docker-compose down
docker-compose up -d
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701503550784/419a2acd-ab03-4900-a216-ec53f24a42ef.jpeg align="center")

And in the Console Output, we can check the status.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701503605525/848e68b2-da46-4695-9f62-affa8f4a2832.jpeg align="center")

The build is successful !!!!!!!!!!!!!!!!!

---

In this blog, I have done a freestyle project on Jenkins to deploy a Django application on Docker. If you have any questions or would like to share your experiences, feel free to leave a comment below. Don't forget to read my blogs and connect with me on LinkedIn and let's have a conversation.

To help me improve my blog and correct my mistakes, I am available on LinkedIn as **Vedant Adhe**. Do reach me and I am open to suggestions and corrections.

#Day23 #90daysofdevops

---