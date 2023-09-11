---
title: "Day-08 of 90DaysofDevOps"
datePublished: Thu Jul 27 2023 05:24:51 GMT+0000 (Coordinated Universal Time)
cuid: clkkpn8sf001109lc6yj6gp0k
slug: day-08-of-90daysofdevops
tags: freshersjobs, trainwithshubham, 90daysofdevops-devops-projectdevelopment-nonitbackground-github-docker-cloudplatforms-ec2-aws-elasticbeanstalk-lambdafunctions-devopspipelines-terraform-jenkins-docker-devsecops-scm-git-gitlab-bitbucket-buildtools-griddle-maven-ant-msbuild-monitoringtools-prometheus-grafana-ansible-ai-chatgpt-valueaddition-realworldproblems, devopsjobs

---

## Boost Your DevOps Career: Getting Started with Git & GitHub

1. what is Git?
    
2. What is GitHub?
    
3. What is Version Control? How many types of version controls we have? 🎮
    
4. Why we use distributed version control over centralized version control? 🎮
    
    1. ### What is Git? 👨🏻‍💻
        

Git is a distributed version control system designed for managing source code and tracking changes in software development projects. It was developed in 2005 by Linus Torvalds to overcome the limitations of existing version control systems.

Simply put, Git allows multiple developers to collaborate on a project simultaneously, tracking all changes made to the code base over time. Each developer has their local copy of the entire project's history, making it possible to work offline without a constant connection to a central server.

Git works on the principle of commits, which are snapshots of the project at a particular point in time. Each commit represents a set of changes made to the code, such as adding new features, fixing bugs, or modifying existing code. These commits are organized into branches so that developers can work independently on individual tasks and later contribute their changes back to the main code base.

1. ### Wat is GitHub? 👨🏻‍💻
    

GitHub is a website and platform where people can store and share their computer code. It is something like a social network for programmers and developers. It allows them to work together on projects, collaborate on code, and track the changes they make to the code over time. GitHub makes it easy for others to see and use the code and is widely used in the tech community to create and improve all kinds of software and applications.

1. ### What is Version Control? How many types of version controls do we have? 🎮
    

Version control is a method of managing changes to documents, software code, or any other type of file. It helps individuals or teams keep track of the different versions of their work and enables them to collaborate more effectively.

Imagine you are working on a project, such as a book or a computer program. As you make changes, you may want to keep track of previous versions in case you need to go back to them or compare different versions. This is where version control comes in.

* ⚙️Centralized version control System (CVCS) : In this type, all files and their versions are stored on a central server. When you want to make changes, you check out a copy of the files from the central server, make your changes, and then check them back in. This ensures that all members of the team have access to the same files and can collaborate. Examples of centralized version control systems include SVN (Subversion) and Perforce.
    

```bash
                           Remote Central Repository
                           +--------------------------------+
                           |                                |
                           |                                |
                           |       Versioned Files          |
                           |       and Project History      |
                           |                                |
                           +--------------------------------+
                                      |
                                      |
                                      v
                           +--------------------------------+
                           |                                |
                           | Local Working Copy (Working    |
                           | Directory with Versioned       |
                           | Files from Remote Repository)  |
                           |                                |
                           +--------------------------------+
                                      |
                                      |
                                      v
                           +--------------------------------+
                           |                                |
                           | Local Changes and Modifications|
                           | to Versioned Files             |
                           |                                |
                           +--------------------------------+
```

* ⚙️Distributed version control System (DVCS): With this type of version control, each team member has their local copy of the entire project, including all file versions. This allows for more flexibility and independence. You can work on your copy, make changes, and when you are done, you can share your changes with others. Others can then incorporate your changes into their copies. Git and Mercurial are popular examples of distributed version control systems.
    
    Both types of version control have their advantages, and the choice depends on the needs and preferences of the team or person using them. Version control plays a critical role in software development, writing, and collaborative projects. It makes it easier to track changes, resolve conflicts, and maintain the history of work done.
    
    ```bash
                 Local Repository 1              Local Repository 2
                +-----------------+            +-----------------+
                |                 |            |                 |
                | Working Copy    |            | Working Copy    |
                |                 |            |                 |
                +-----------------+            +-----------------+
                         |                               |
                         |                               |
                         v                               v
                +-----------------+            +-----------------+
                |                 |            |                 |
                | Staging Area    |            | Staging Area    |
                |                 |            |                 |
                +-----------------+            +-----------------+
                         |                               |
                         |                               |
                         v                               v
                +-----------------+            +-----------------+
                |                 |            |                 |
                | Local History   |            | Local History   |
                | (Versioned)     |            | (Versioned)     |
                +-----------------+            +-----------------+
                         |                               |
                         |                               |
                         v                               v
                +--------------------------------------------+
                |                                            |
                |             Remote Repository              |
                |                                            |
                +--------------------------------------------+
    ```
    
    1. ### Why do we use distributed version control over centralized version control? 🎮
        
    
      
    Simply put, we prefer distributed version control to centralized version control because it offers some significant advantages.
    
    Distributed version control allows multiple people to work on the same project without requiring a constant Internet connection to a central server. Each person has their own copy of the entire project, including all history. This means that if the main server goes down or there are network problems, everyone can continue working independently and synchronize their changes later when the server is working again.
    
    Centralized version control, on the other hand, relies heavily on a single central server. If a problem occurs on that server, everyone's work can come to a halt until the server is fixed. This can cause frustrating delays and interruptions in a team's workflow.
    
    With distributed version control, developers can work more efficiently and collaboratively. They can experiment with new features and changes without affecting the main project until they are ready. It also makes branching and merging versions much easier, as teams can work on different features simultaneously and merge their changes seamlessly later.
    
    Overall, distributed version control offers more flexibility, resilience, and speed, making it the preferred choice for many modern software development teams.
    

### **Some Basic Commands of Git.**

```bash
git init: Initializes a new Git repository in the current directory, creating a hidden 

git clone : Copies a remote repository to your local machine, creating a new directory with the repository's contents.

git add : Adds file(s) to the staging area, preparing them for the next commit.

git status: Shows the current status of the repository, including changes, files in the staging area, and untracked files.

git commit -m "commit message": Creates a new commit with the changes from the staging area and adds a brief commit message describing the changes.

git push: Sends your committed changes to the remote repository.

git pull: Fetches and merges changes from the remote repository into your local branch.

git branch: Lists all branches in the repository and indicates the current branch with an asterisk.

git checkout: Switches to the specified branch.

git merge : Merges the specified branch into the current branch.

git log: Displays a history of commits in the current branch, showing commit IDs, authors, dates, and commit messages.

git remote: Lists the remote repositories linked to your local repository.

git remote add : Adds a new remote repository with a given name and URL.

git remote remove: Removes a remote repository from your local configuration.

git diff: Shows the differences between your working directory and the staging area.

git diff --staged: Displays the differences between the staging area and the last commit.

git reset: Unstages a file, removing it from the staging area but preserving its changes in the working directory.

git rm : Removes a file from both the working directory and the repository, preparing it for the next commit.

git config: Allows you to set and view configuration options for Git, such as your name and email.
```

### Task : **Create a new repository on GitHub and clone it to your local machine**

Step 1 : Sign in to your GitHub account using your username and password.

**step 2:** Once you are signed in, click on the “+” icon in the top-right corner of the GitHub homepage. From the dropdown menu, select “New repository.” or, go to repositories and click on ‘new’ in the top right corner.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690434547235/82036894-31aa-45d6-b63a-391389723f3e.png align="center")

**Step 3:** Set up the repository: Now Add the repository name and other details like whether you want to keep it a public or private repo.

Then click on ‘Create repository

you have successfully created a repository.

**step 4:** After creating the Repository it will look something like this :

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690434768162/04125c19-678a-454b-9b4f-2f62b59412dd.png align="center")

### **Clone Repo to the local machine**

**step1:** click on &lt;&gt;code, after that, we can see a path, and copy that path

**step 2:** let's go into your local machine.

**step 3:** git clone &lt;[https://github.com/exampleuser/my-repository.git](https://github.com/exampleuser/my-repository.git)\&gt;

it will clone your repository into your local.

### **Make some changes to a file in the repository and commit them to the repository using Git**

Create a few files or do the code you want to and then commit them.

We have created 2 files and added a few line of code in each file.

```bash
git add example.txt
```

```bash
git commit -m "Add descriptive commit message here"
```

```bash
git push
```

### **Conclusion:**

Above mentioned information is much important for a DevOps engineer as he has You’ve mastered the art of Git and GitHub, joining the ranks of legendary DevOps engineers! Embrace version control and collaboration, and your coding adventures shall know no bounds!

I also received comprehensive training in various aspects of DevOps methodologies, including continuous integration, continuous deployment, and infrastructure automation. Stay connected with me for more interesting articles about Cloud and DevOps by following me on Hashnode,

LinkedIn ([**linkedin.com/in/vedant-adhe-4683b0192**](http://linkedin.com/in/vedant-adhe-4683b0192)**) and**

**GitHub (**[**github.com/VedantAdhe**](http://github.com/VedantAdhe)**)**

**Connect** [**Vedantadhe19@gmail.com**](mailto:Vedantadhe19@gmail.com)

Thank You For Reading! Continue to Support Us, Learn From Each Other and Grow Together