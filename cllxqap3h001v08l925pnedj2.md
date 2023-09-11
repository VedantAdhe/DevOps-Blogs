---
title: "Day-16 For 90 Day's of DevOps

Diving Deep into Docker: Empowering DevOps Engineers"
datePublished: Wed Aug 30 2023 12:43:47 GMT+0000 (Coordinated Universal Time)
cuid: cllxqap3h001v08l925pnedj2
slug: day-16-for-90-days-of-devops-diving-deep-into-docker-empowering-devops-engineers
tags: devops-articles, trainwithshubham

---

The `docker run` command is used to start a new container based on a specified Docker image. It allows you to define various options and configurations for the container.

Example:

```bash
docker run hello-Docker
```

---

### **Docker inspect command:**

When you run the `docker inspect` command, it will return a comprehensive JSON output that includes various details about the specified Docker object. This information can include things like configuration settings, network details, storage paths, labels, environment variables, and more.

For example, to inspect a Docker container with the name "my\_container," you would run:

```bash
docker inspect my_container
```

---

### **Docker port command:**

The `docker port` command is used to inspect the mapping of ports between a running container and the host system. It allows you to see which ports inside the container are being forwarded to specific ports on the host machine. This is particularly useful when you have services running within a Docker container that you want to access from your local machine or from other networked devices.

The basic syntax of the `docker port` command is:

```bash
docker port <container_name_or_id>
```

---

### **Docker stats command:**

The docker stats command is used to display real-time resource usage statistics for running containers. It provides information such as CPU usage, memory consumption, network I/O, and block I/O of each container.

```bash
docker stats
```

---

### **Docker top command:**

The docker top command is used to display running processes inside the container. This command does not provide real-time updates. For that one needs to use the docker stats command.

```bash
docker top container_id
```

---

### **Docker save command:**

We use the docker save command to save one or more docker images to a tar archive.

```bash
docker save -o image.tar image:tag
```

---

### **Docker load command:**

The docker load command restores the saved images into your local Docker environment, making them available for use.

```bash
docker load -i image.tar
```

---