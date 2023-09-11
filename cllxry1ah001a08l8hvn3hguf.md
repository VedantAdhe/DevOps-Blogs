---
title: "Day-18 For 90 Day's  of DevOps

         Docker Compose for DevOps Engineers"
datePublished: Wed Aug 30 2023 13:29:56 GMT+0000 (Coordinated Universal Time)
cuid: cllxry1ah001a08l8hvn3hguf
slug: day-18-for-90-days-of-devops-docker-compose-for-devops-engineers
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1693920793264/afe49129-de3f-4d7e-96a6-034480454da5.png
tags: devops, devopscommunity

---

---

# **Docker Compose:**

Docker Compose is a tool that lets you create and manage complex applications that consist of multiple containers. With Docker Compose, you can write a YAML file that specifies the services, networks, volumes, and other options for your application. Then, with a single command, you can build, run, and scale your application as a whole.

Docker Compose is useful for developing, testing, and deploying applications that have multiple components or microservices. For example, you can use Docker Compose to create a web application that consists of a web server, a database, and a cache. You can also use Docker Compose to orchestrate the communication and dependencies between different containers.

---

## **Working of Docker Compose:**

Using Docker-Compose is essentially a three-step process:

1. Define your app’s environment with a `Dockerfile` so it can be reproduced anywhere.
    
2. Define the services that make up your app in `docker-compose.yml` so they can be run together in an isolated environment.
    
3. Run `docker compose up` and the Docker compose command starts and runs your entire app. You can alternatively run `docker-compose up` using Compose standalone(`docker-compose` binary).
    

---

## **What is YAML?**

YAML stands for Yet Another Markup Language or YAML Ain’t Markup Language (a recursive acronym), depending on whom you ask. YAML is a data serialization language that is designed to be easy to read and write by humans. YAML is commonly used for writing configuration files and in applications where data is being stored or transmitted.

YAML has a simple syntax that uses indentation, colons, dashes, and brackets to represent the structure and values of data. YAML supports scalars (such as strings, numbers, and booleans), lists (or sequences), and maps (or dictionaries). YAML also allows you to define custom data types and aliases for reusing data.

Here is an example of a YAML file that defines some information about a person:

```bash
name: Jerry
age: 25
gender: male
hobbies:
  - Blog
  - Cricket
  - gardening
address:
  street: 101 Main Street
  city: toronto
  state: Canada
  zip: 45012
```

---

## **Learn how to use the docker-compose.yml file**

In this task, you will learn how to use the docker-compose.yml file to set up the environment, configure the services and links between different containers, and also to use environment variables in the docker-compose.yml file.

The docker-compose.yml file is the main file that defines your application using Docker Compose. It follows the YAML syntax and has a specific format that you can find at [**Compose file reference**](https://docs.docker.com/compose/).

A typical docker-compose.yml file looks something like this:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693401959863/3156d236-bf45-429f-b60d-d004f0a10a6a.png align="center")

This file defines an application that consists of three services:

* web: A web server that uses the nginx image and exposes port 80 on the host machine. It depends on the app service.
    
* app: A web application that uses a custom image built from the Dockerfile in the ./app directory. It passes some environment variables related to the database connection and mounts the ./app directory as a volume on the container.
    
* db: A database server that uses the mysql image and passes some environment variables related to the database creation and password. It uses a named volume called db\_data to persist its data.
    

The file also defines a named volume called db\_data and a default network using the bridge driver.

To run this application using Docker Compose, you need to navigate to the directory where your docker-compose.yml file is located, and then run this command:

```bash
docker compose up
```

This will create and start all the services defined in your file. You can also use the -d flag to run the services in detached mode, which means they run in the background.

To stop and remove the services, you can run this command:

```bash
docker compose down
```

---

## **Conclusion**

In this blog, I have shown you how to use Docker Compose and YAML to define and run multi-container applications with Docker. I have also shown you how to pull an existing Docker image from a public repository and run it on your local machine as a non-root user. I have also shown you how to inspect, log, stop, start, and remove containers using Docker commands.

I hope you have learned something new and useful from this blog. If you have any questions or feedback, please feel free to leave a comment below