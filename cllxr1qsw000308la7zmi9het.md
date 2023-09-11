---
title: "Day-17 For 90 Day's of DevOps

           Docker Project for DevOps Engineers"
datePublished: Wed Aug 30 2023 13:04:49 GMT+0000 (Coordinated Universal Time)
cuid: cllxr1qsw000308la7zmi9het
slug: day-17-for-90-days-of-devops-docker-project-for-devops-engineers
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1693829729815/abd37669-f54d-4f21-b8c5-cc53fbd2bdb3.jpeg
tags: devops, trainwithshubham

---

---

In this blog, let’s learn about what a Dockerfile is and use the dockerfile to create a container.

---

## Dockerfile

A Dockerfile is a text file used to define a set of instructions to build a Docker image. When we use the Docker command-line interface (CLI) to build an image, it reads the instructions from the Dockerfile and executes them to create the image. The name of the docker file will always be *dockerfile* and nothing else.A dockerfile will have instructions written in the following format:

```bash
keyword argument
```

A dockerfile will always start with FROM and FROM can only be used once. A RUN keyword can be used multiple times. But wait, what are these keywords? To understand that I have created the dockerfile format:

```bash
FROM 
RUN 
ENV 
WORKDIR 
COPY 
ADD 
CMD 
ENTRYPOINT 
(Port) EXPOSE 
VOLUME
```

---

## FROM:

FROM is the mandatory keyword. FROM specifies the Base Image that the Docker images are to be built from according to our customization. Docker images are never built from scratch, they are built on base images. Below is an example of how to use the keyword FROM:

```bash
FROM ubuntu
```

---

## RUN:

RUN is a keyword that can be repeated multiple times. It is used to provide the Linux commands like installing a package, uninstalling, upgrading a package, creating a directory, or permitting users. Below is an example of how to use the keyword RUN:

```bash
RUN apt-get update
```

---

## **WORKDIR:**

WORKDIR is used to specify the default directory where the commands will be executed. Below is an example of how to use the keyword WORKDIR:

```bash
WORKDIR /path/to/workdir
```

If the WORKDIR is not specified, it will be created automatically by the Docker compiler and the default will be the ROOT directory (`/`).

---

## **COPY:**

COPY is used to copy files from the host machine to the container directory.

---

## **ADD:**

ADD is used to copy files from the host machine to the container directory and it can also copy TAR files and unzip them on the container directory.

---

## **CMD:**

By using the keyword CMD, we will provide the commands or name of the script that *should run when the container is launched.* This can be overwritten by the user.

---

## **EXPOSE:**

The keyword EXPOSE specifies the port number that needs to be exposed on the container.

---

## **ENTRYPOINT:**

The commands get executed post-container launch while using the keyword ENTRYPOINT. It cannot be overwritten and a new command can be appended.

---

## **VOLUME:**

The keyword VOLUME is used to inform users of the Docker image that certain directories within the container should be treated as volumes when running a container based on that image.

---

# **Task: Create a Dockerfile for a simple web application**

Build the image using the Dockerfile and run the container.

Verify that the application is working as expected by accessing it in a web browser.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693400568302/eb4ed62c-6fea-46d8-8538-2486ce891955.png align="center")