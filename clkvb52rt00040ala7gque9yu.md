---
title: "Day-11 of 90DaysofDevops"
datePublished: Thu Aug 03 2023 15:24:16 GMT+0000 (Coordinated Universal Time)
cuid: clkvb52rt00040ala7gque9yu
slug: day-11-of-90daysofdevops
tags: devops, 90daysofdevops, trainwithshubham-techwithankush-seekhoaursikhao-twscommunitybuilders-90daysofdevops-connections-growth-community-learning-linkedin-devops-awsdevops-awscloud-awscommunity-aws-docker-dockercontainer-dockerhub-kubernetescluster-kubernetesservices-kubernetes-jenkins-ansible-ansibleautomates-linuxsystemadministration-linuxfoundation-linux-git-github-terraform-grafana-prometheus-cicd-cicdpipelines, devops-job

---

# Unleashing the Power of Git & GitHub in DevOps

### Git Stach :

**Git stash** is a feature in the Git version control system that allows developers to save their current changes temporarily and switch to a different branch or task without committing those changes. It acts as a "clipboard" for code changes that have not been committed, enabling developers to store their work in progress safely.

When working on a specific task or branch, developers might need to switch to another branch or perform a different task that is not yet ready for a commit. Instead of committing incomplete or experimental changes, which could lead to messy commit history, they can use Git stash to store the changes in a special area called the "stash."

The stash can hold changes to both tracked (already added to the repository) and untracked (new or ignored) files. It captures modifications to files, new files, and deletions, preserving the state of the working directory and the index.

Once the changes are stashed, the working directory is clean, and the developer can switch branches or perform other tasks. Later, they can apply the stash back to the working directory, restoring the changes exactly as they were, allowing for further development or commit.

### **Cherry-pick**:

**Git cherry-pick** is particularly useful when you want to bring specific changes from one branch to another without merging the entire branch, which can be beneficial in situations like backporting bug fixes, introducing specific features to different branches, or applying hotfixes to multiple release branches.

It is essential to use cherry-pick judiciously and understand its implications, especially in scenarios where the same changes have already been applied to other branches. Cherry-picking can lead to duplicate commits and potential merge conflicts down the line, so it's crucial to consider the context and version control strategy before utilizing this command.

### **Resolving Conflicts :**

Resolving Conflicts in the context of version control systems, such as Git, refers to the process of addressing and resolving conflicting changes made to the same part of a file or set of files by different contributors.

When multiple developers are working on the same project simultaneously, there is a possibility that they may modify the same lines of code or files independently. When these changes are merged into the main codebase or pulled from a remote repository, a conflict arises because the version control system cannot automatically determine which changes to keep and which to discard.

It's important to communicate with other developers when resolving conflicts, especially if the conflicting changes have significant impacts on the project. Collaborative resolution ensures that everyone is aware of the changes made and that the project maintains its integrity.

Resolving conflicts is a crucial part of collaborative software development, and mastering this skill ensures a smooth and efficient version control process, promoting teamwork and seamless integration of contributions.

Task -01

Create a new branch and switch to it:

```bash
# Create a new branch and switch to it
git checkout -b my_new_branch
```

1. Make some changes to the files in the new branch.
    
2. Use git stash to save the changes without committing them:
    

```bash
# Stash the changes in the new branch
git stash save "My changes in my_new_branch"
```

Switch to a different branch (e.g., the main branch):

```bash
# Switch to a different branch (e.g., main branch)
git checkout main
```

Make some changes to the files in the main branch and commit them:

```bash
# Make some changes to the files
# ...

# Add the changes to the staging area
git add .

# Commit the changes
git commit -m "Commit on the main branch"
```

Switch back to the new branch (my\_new\_branch):

```bash
# Switch back to the new branch
git checkout my_new_branch
```

Use git stash pop to bring the changes back and apply them on top of the new commits:

```bash
# Apply the stashed changes on top of the new commits
git stash pop
```

Task 2: To cherry-pick the commit "Added feature2.2 in development branch" into the Production branch and apply the specified changes, follow the steps below:

Step 1: Check out the Production branch

```bash
git checkout production
```

Step 2: Cherry-pick the commit "Added feature2.2 in development branch"

```bash
git cherry-pick <commit-hash>
```

Replace `<commit-hash>` with the actual commit hash of "Added feature2.2 in development branch.

Step 3: Open the file that was changed in the cherry-picked commit (e.g., the file where "Added feature2.2 in development branch" was made).

Step 4: Edit the file and add the requested lines after Line3 and Line4:

```bash
- Line to be added after Line3>> This is the advancement of previous feature
- Line4>>Added few more changes to make it more optimized.
```

Step 5: Save the changes.

Step 6: Commit the changes with an appropriate commit message:

```bash
git commit -m "Optimized the feature"
```

Step 7: If you encounter any conflicts during the cherry-pick or editing process, resolve them and use `git add` to stage the resolved changes before committing.

Step 8: Push the changes to the remote Production branch (if necessary):

```bash
git push origin production
```