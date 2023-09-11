---
title: "Day 10 of 90 Day's of DevOps"
datePublished: Tue Aug 01 2023 14:43:14 GMT+0000 (Coordinated Universal Time)
cuid: clksesl6o000109l70qgpatq2
slug: day-10-of-90-days-of-devops
tags: devopscommunity, trainwithshubham-techwithankush-seekhoaursikhao-twscommunitybuilders-90daysofdevops-connections-growth-community-learning-linkedin-devops-awsdevops-awscloud-awscommunity-aws-docker-dockercontainer-dockerhub-kubernetescluster-kubernetesservices-kubernetes-jenkins-ansible-ansibleautomates-linuxsystemadministration-linuxfoundation-linux-git-github-terraform-grafana-prometheus-cicd-cicdpipelines

---

## Advanced Git & GitHub for Successful DevOps

1. What is Git Branching?
    
2. Git Revert and Reset
    
3. Git Rebase and Merge
    

1. What is Git Branching?
    

Imagine you're working on a project, and you want to add some new features to it. Instead of making these changes directly to the main codebase, Git allows you to create a separate "branch" where you can make your modifications independently. A branch is like a separate timeline where you can experiment and make changes without disrupting the rest of the project. This is similar to writing a draft of your essay on a separate piece of paper before finalizing it on the main document.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690898918552/0ac01989-d367-4382-a8d3-f13d3aafa78b.png align="center")

Here's a step-by-step guide to the basic branching workflow:

1. Main/Branch: This is the primary branch, usually named "main" or "master." It represents the stable and deployable version of the project. It is essential to keep the main branch clean and free from any experimental or untested changes.
    
2. Feature/Branch: These are branches created for specific features or tasks. Each time you start working on something new, you create a feature branch from the main branch. Once your work is complete, you can merge the feature branch back into the main branch.
    

## Git Revert and Reset

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690900310854/b6492abf-667b-4e59-907b-048642f1a293.png align="center")

Git is a powerful version control system used by developers around the world to efficiently manage their projects. As you dive deeper into Git, you'll come across terms like "revert" and "reset" that might seem intimidating at first. But fear not! In this blog post, we'll explain the Git commands "revert" and "reset" in simple language so you can use them confidently in your development workflow.

1. ## What is version control?
    

Before we get into the specific commands of Git, let's briefly understand the concept of version control. Version control allows developers to track changes to their codebase over time, which facilitates collaboration and allows them to revert to a previous state if needed. Git is a distributed version control system, which means that it stores the entire history of your project on each developer's machine.

### **Git revert**

Imagine you are working on a feature in your project and realize that some of your recent changes have caused problems. You want to undo those changes without changing the rest of your codebase. This is where the "git revert" command comes in.

When you "revert" a commit, Git creates a new commit that reverts the changes made in the specified commit. This does not remove the original commit but creates a new commit that reverts the changes introduced by the old commit.

The syntax for reverting a commit is simple:

```bash
git revert <commit-id>
```

### **Git reset**

Let's now move on to "git reset" This command is more powerful and should be used with caution. Unlike "git revert" which creates new commits, "git reset" changes the project history by moving the branch pointer to another commit.

"Git reset" comes in three flavors: --soft, --mixed (default), and --hard.

\--soft reset: This option moves the branch pointer to the specified commit, but leaves changes made after that commit in the staging area. This allows you to make further adjustments before committing them.

### **Git Rebase and Merge**

### What Is Git Rebase?

Git rebase is a command that lets users integrate changes from one branch to another, and the logs are modified once the action is complete. Git rebase was developed to overcome merging’s shortcomings, specifically regarding logs.

### What Is Git Merge?

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690900367797/57ab150d-173b-4f92-99ef-37b7c1321cac.png align="center")

Git merge is a command that allows developers to merge Git branches while the logs of commits on branches remain intact. The merge wording can be confusing because we have two methods of merging branches, and one of those ways is actually called “merge,” even though both procedures do essentially the same thing.

```markdown
git checkout <Branch name>
git merge <Filename>
```

#### **Day 10 tasks we will cover the following things :**

Task 1 : Create a text file called `version01.txt` inside the `Devops/Git/` directory with the content "This is the first feature of our application."

```bash
echo "This is the first feature of our application" > Devops/Git/version01.txt
```

Create a new branch called `dev` from the `master` branch.

```bash
git checkout -b dev
```

Add and commit the changes in the `dev` branch.

```bash
git add Devops/Git/version01.txt
git commit -m "Added new feature"
```

Push the `dev` branch to the remote repository for review.

```bash
git push origin dev
```

Add and commit the changes in the `dev` branch.

```bash
git add Devops/Git/version01.txt
git commit -m "Added new feature"
```

Push the `dev` branch to the remote repository for review.

```bash
git push origin dev
```

Add new commits in the `dev` branch by editing the `version01.txt` file as described:..

```bash
# Edit the file to add the mentioned lines
echo "This is the bug fix in development branch" >> Devops/Git/version01.txt
git add Devops/Git/version01.txt
git commit -m "Added feature2 in development branch"

echo "This is gadbad code" >> Devops/Git/version01.txt
git add Devops/Git/version01.txt
git commit -m "Added feature3 in development branch"

echo "This feature will gadbad everything from now." >> Devops/Git/version01.txt
git add Devops/Git/version01.txt
git commit -m "Added feature4 in development branch"
```

To restore the file to a previous version where the content is "This is the bug fix in the development branch," you can use the `git reset` command.

```bash
# Find the commit hash of the version you want to revert to (the one with "This is the bug fix in development branch")
git log

# Use the commit hash to reset the file
git reset --hard <commit_hash>
```

`git reset --hard` command will discard any uncommitted changes, so make sure to back up any important changes before running it. Additionally, if you prefer to keep the changes and revert the commit without losing the work, you can use `git revert` instead of `git reset`.

In this blog post, you have learned some of the advanced skills and techniques for using Git and GitHub as a DevOps Engineer.

You have learned how to:

Create and manage branches for different features and bug fixes

Undo and revert your changes to a previous state

Rebase and merge your branches to keep your history clean and avoid conflicts

I hope you enjoyed this blog post and learned something new. If you have any questions or suggestions, feel free to leave a comment below or contact me on LinkedIn or GitHub. I would love to hear from you!

LinkedIn ([**linkedin.com/in/vedant-adhe-4683b0192**](http://linkedin.com/in/vedant-adhe-4683b0192)**) and**

**GitHub (**[**github.com/VedantAdhe**](http://github.com/VedantAdhe)**)**

**Connect** [**Vedantadhe19@gmail.com**](mailto:Vedantadhe19@gmail.com)

Thank you for reading and happy coding!