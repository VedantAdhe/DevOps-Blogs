---
title: "Day-21 Docker Important interview Questions"
datePublished: Fri Sep 08 2023 15:04:24 GMT+0000 (Coordinated Universal Time)
cuid: clmaqa6k6000809l2cs6yhc8h
slug: day-21-docker-important-interview-questions
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1694185453559/26019c81-6b1a-4fca-b6b4-a0ec4d0d5d03.png
tags: trainwithshubham-techwithankush-seekhoaursikhao-twscommunitybuilders-90daysofdevops-connections-growth-community-learning-linkedin-devops-awsdevops-awscloud-awscommunity-aws-docker-dockercontainer-dockerhub-kubernetescluster-kubernetesservices-kubernetes-jenkins-ansible-ansibleautomates-linuxsystemadministration-linuxfoundation-linux-git-github-terraform-grafana-prometheus-cicd-cicdpipelines

---

1. **Difference between Image, Container, and Engine:**
    
    * **Docker Image:** A Docker image is a lightweight, stand-alone, and executable package that contains all the necessary components to run a piece of software, including the code, runtime, system tools, libraries, and settings. Images are read-only and serve as the blueprint for creating containers.
        
    * **Docker Container:** A Docker container is a runnable instance of a Docker image. It encapsulates an application and its dependencies, isolating it from the host system and other containers. Containers are lightweight, start quickly, and can be easily moved between different environments.
        
    * **Docker Engine:** Docker Engine is the core component of Docker that enables the creation and management of Docker containers. It includes the Docker daemon (dockerd) responsible for building, running, and managing containers, as well as the Docker CLI (Command Line Interface) for interacting with the Docker daemon.
        
2. **Difference between Docker** `COPY` **vs** `ADD` Commands:
    
    * `COPY`: The `COPY` command in a Dockerfile is used to copy files and directories from the host system into the image. It's a simple and straightforward way to add files to the image, but it doesn't support some of the advanced features that `ADD` does.
        
    * `ADD`: The `ADD` command in a Dockerfile also copies files and directories from the host system into the image. Additionally, it can perform automatic extraction of compressed files and download files from remote URLs. While `ADD` offers more functionality, it's recommended to use `COPY` for simple file copying to ensure transparency in the build process.
        
3. **Difference between Docker** `CMD` **vs** `RUN` Commands:
    
    * `RUN`: The `RUN` command is used in a Dockerfile to execute commands during the image build process. It's typically used to install packages, configure the environment, and perform setup tasks. The commands specified with `RUN` are executed once during image creation.
        
    * `CMD`: The `CMD` command in a Dockerfile defines the default command to run when a container is started from the image. It specifies the executable and any arguments. You can only have one `CMD` instruction in a Dockerfile, and it can be overridden when running a container by providing a command as an argument.
        
4. **Reducing the Size of Docker Image:** To reduce the size of a Docker image, you can follow these practices:
    
    * Use multi-stage builds to discard unnecessary build artifacts.
        
    * Minimize the number of layers by combining commands and cleaning up after each step.
        
    * Use Alpine Linux as a base image, as it's lightweight.
        
    * Remove unnecessary files and dependencies.
        
    * Use a smaller base image when possible.
        
    * Avoid installing unnecessary packages and dependencies.
        
    * Compress and optimize files within the image.
        
    * Regularly update and patch base images to include security fixes.
        
5. **Why and When to Use Docker:** Docker is used for:
    
    * **Application Isolation:** To isolate applications and their dependencies, ensuring consistency across different environments.
        
    * **Portability:** To package applications into containers that can run consistently on various platforms.
        
    * **Ease of Deployment:** To simplify the deployment and scaling of applications.
        
    * **Resource Efficiency:** To maximize resource utilization by running multiple containers on a single host.
        
    * **DevOps and CI/CD:** To streamline development, testing, and deployment processes.
        
    * **Microservices:** To build and deploy microservices-based architectures.
        
6. **Docker Components and Their Interaction:**
    
    * **Docker Engine:** Manages containers and images.
        
    * **Docker Daemon (**`dockerd`): Listens for Docker API requests and manages containers and images.
        
    * **Docker CLI (**`docker`): Allows users to interact with Docker by issuing commands.
        
    * **Docker Registry:** Stores Docker images, such as Docker Hub.
        
    * **Docker Image:** A read-only blueprint for creating containers.
        
    * **Docker Container:** Runnable instances of Docker images.
        
    * **Docker Compose:** A tool for defining and running multi-container applications.
        
7. **Terminology:**
    
    * **Docker Compose:** A tool for defining and running multi-container Docker applications using a YAML file.
        
    * **Dockerfile:** A script used to create a Docker image.
        
    * **Docker Image:** A snapshot of a file system with application code and dependencies.
        
    * **Docker Container:** An executable instance of a Docker image.
        
8. **Real Scenarios of Using Docker:**
    
    * Deploying web applications with consistent environments.
        
    * Running databases in isolated containers.
        
    * Setting up development environments.
        
    * Building and deploying microservices.
        
    * Creating scalable and reproducible testing environments.
        
9. **Docker vs. Hypervisor:**
    
    * Docker uses containerization to run applications in isolated environments, sharing the host OS kernel, making it more lightweight and efficient.
        
    * Hypervisors, like VMware and VirtualBox, create virtual machines (VMs) with their own OS, consuming more resources and being less efficient than containers.
        
    * Docker containers start quickly and have less overhead, while VMs require more time and resources to boot.
        
    * Docker is often preferred for microservices and cloud-native applications, while hypervisors are used for running multiple OS instances.
        
10. **Advantages and Disadvantages of Docker:**
    
    * **Advantages:**
        
        * Portability and consistency.
            
        * Isolation and security.
            
        * Resource efficiency.
            
        * Rapid deployment.
            
        * Scalability.
            
        * Easy management with orchestration tools.
            
    * **Disadvantages:**
        
        * Limited to Linux and Windows Server hosts.
            
        * Not suitable for all types of applications.
            
        * Complexity in networking and storage configuration.
            
        * Requires a learning curve.
            
11. **Docker Namespace:**
    
    * A Docker namespace is a mechanism that provides isolation for various aspects of a container, such as the file system, process IDs, user IDs, and network. Namespaces ensure that processes running within a container are isolated from the host and other containers.
        
12. **Docker Registry:**
    
    * A Docker registry is a repository for storing and distributing Docker images. Docker Hub is a popular public registry, but you can also set up private registries to store your own images.
        
13. **Entry Point:**
    
    * The entry point in a Dockerfile defines the command that will be executed when a container is started from the image. It can include an executable and its arguments. The entry point can be overridden when running a container by specifying a different command.
        
14. **Implementing CI/CD in Docker:**
    
    * Implement CI/CD in Docker by using tools like Jenkins, GitLab CI/CD, or Travis CI to automate building, testing, and deploying Docker containers.
        
    * Create Docker images in the CI/CD pipeline.
        
    * Push images to a Docker registry.
        
    * Deploy containers to target environments using orchestration tools like Kubernetes or Docker Swarm.
        
15. **Data Persistence in Docker Container:**
    
    * By default, data within a Docker container is stored in the container's writable layer, and it will be lost when the container exits. To persist data, you can use Docker volumes or bind mounts to map host directories or external storage to specific paths in the container.
        
16. **Docker Swarm:**
    
    * Docker Swarm is Docker's native container orchestration tool for managing and scaling containers in a cluster. It allows you to create and manage a swarm of Docker nodes as a single virtual system.
        
17. **Common Docker Commands:**
    

* View running containers: `docker ps`
    
* Run a container with a specific name: `docker run --name <container_name> <image_name>`
    
* Export a Docker container: `docker export <container_id> > <output_file>`
    
* Import an existing Docker image: `docker import <input_file> <repository:tag>`
    
* Delete a container: `docker rm <container_id>`
    
* Remove stopped containers, unused networks, build caches, and dangling images: `docker system prune`
    

1. **Common Practices to Reduce Docker Image Size:**
    
    * Use multi-stage builds.
        
    * Choose a minimal base image (e.g., Alpine Linux).
        
    * Remove unnecessary files and dependencies.
        
    * Combine RUN commands to minimize layers.
        
    * Use smaller, efficient libraries.
        
    * Clean up temporary files and caches in the same RUN instruction.
        
    * Minimize the number of installed packages.
        
    * Use .dockerignore to exclude unneeded files from the build context.