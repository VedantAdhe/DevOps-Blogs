---
title: "Deploying a Reddit Clone Web App on a Kubernetes Cluster with Ingress"
datePublished: Sat Sep 09 2023 12:58:00 GMT+0000 (Coordinated Universal Time)
cuid: clmc17hy1000e09l54htb2hn2
slug: deploying-a-reddit-clone-web-app-on-a-kubernetes-cluster-with-ingress
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1694264270265/d0b55f84-651d-47d8-80f1-f33efe5c0092.jpeg
tags: projects, kubernetes, trainwithshubham-techwithankush-seekhoaursikhao-twscommunitybuilders-90daysofdevops-connections-growth-community-learning-linkedin-devops-awsdevops-awscloud-awscommunity-aws-docker-dockercontainer-dockerhub-kubernetescluster-kubernetesservices-kubernetes-jenkins-ansible-ansibleautomates-linuxsystemadministration-linuxfoundation-linux-git-github-terraform-grafana-prometheus-cicd-cicdpipelines

---

### Overview of The Project

This project entails the deployment of a Reddit clone web application on a Kubernetes cluster with the use of Ingress. Kubernetes, a widely used open-source container orchestration platform, streamlines the deployment and management of containerized applications. Ingress, on the other hand, is a Kubernetes component that serves as a reverse proxy, directing incoming HTTP and HTTPS traffic to the relevant services within the cluster. Throughout this project, we will establish a Kubernetes cluster, employ Docker containers to deploy the Reddit clone web application and configure Ingress to efficiently manage incoming traffic by routing it to the appropriate services. The outcome will be a robust and scalable Reddit clone web application, capable of handling substantial traffic loads with resilience.

---

### **Prerequisites:**

1. GitHub
    
2. Two EC2 Instances
    
3. Instance ( AMI - Ubuntu, Type-t2.micro)
    
4. Instance ( AMI - Ubuntu, Type-t2.medium)
    
5. Docker
    
6. Minikube and kubectl
    

---

### **Step 1:** Launch an instance CI-server having Ubuntu AMI, t2.micro instance type(1 CPU, 1GiB RAM) & an instance Deployment-server having Ubuntu AMI, t2.xlarge instance type(4CPU, 16GiB RAM).

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694261262845/1d07aea2-d2aa-4949-9fef-6d4a27fb4b73.png align="center")

### **Step 2:** Connect the CI-server instance and install Docker in it using the command.

* sudo apt-get update
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694261336062/0f5103bc-cc7b-4387-866b-f79a026f885b.png align="center")

* sudo apt-get install [docker.io](http://docker.io) -y
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694261346630/0c5051a1-bc6c-46ed-a1b7-d561b5c298ae.png align="center")

* sudo usermod -aG docker $USER && newgrp docker
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694261357508/c301c701-bc9d-46a6-b01b-ee7e85698d28.png align="center")

* ### Step 3: Clone the Source code of the project
    

Clone the repository from the developer's side and get the code ready on this server, & execute the commands as shown below.

```bash

https://github.com/VedantAdhe/reddit-clone-k8s-ingress.git
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694261449341/134af65e-cf40-4155-901a-aac4fed16528.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694261554854/006d0389-582a-4124-8c70-526fb0ab70a9.png align="center")

---

## **Step 4: Build the Dockerfile**

The project folder includes a Dockerfile that will be used to build the image.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694261657289/001cb705-3d0e-4cd4-a00a-c0154151bc95.png align="center")

```bash

FROM node:19-alpine3.15

WORKDIR /reddit-clone

COPY . /reddit-clone

RUN npm install 

EXPOSE 3000

CMD ["npm","run","dev"]
```

Run the below-given commands inside the root of the project folder to build the docker image, replace the placeholder `<username>` with your DockerHub username.

```bash
docker build . -t <username>/reddit-clone:latest
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694261736271/defa1bf0-ca4e-4737-a003-eb33a9745ff1.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694261754943/06d33a92-2b51-43bc-a7b4-272708a5d776.png align="center")

---

## **Step 5: Push the docker image to Docker Hub**

After building the image, we need to push it to docker hub, our Kubernetes deployment will later fetch the same image from docker hub to run the app.

**Login to DockerHub from docker CLI:**

This step is crucial to push docker images. Run the given command to log in to docker hub with your username and password. `docker login`

**Push the Docker image to DockerHub:**

Use the command `docker push <username>/reddit-clone:latest` to push the image, replace the placeholder `<username>` with your username.

After pushing the image, refresh your DockerHub website, and you will be able to see a new repository has been created containing your docker image.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694261811791/f48786e8-7606-4c43-8563-d08b4a6bd43e.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694262010662/771baa30-0a53-4753-8c28-375f4fc6e486.png align="center")

---

## **Step 6: Creating a Deployment Manifest for K8s**

Congratulations on your achievement! 🥳 You've just accomplished a significant milestone by successfully creating a Docker image and uploading it to Docker Hub, marking the essential stages of the continuous integration process.

Next, our attention turns to deploying the Docker image within a Kubernetes (K8s) cluster. To achieve this, we will leverage Kubernetes' Deployment object to generate Pods that execute our Docker image.

### **What is a Deployment?**

In Kubernetes (often abbreviated as K8s), a Deployment object serves as a controller responsible for managing the lifecycle of Pods. Its primary role is to maintain a specified number of Pod replicas, each running the desired container images. When a Pod faces issues or requires updates, the Deployment takes care of these tasks seamlessly, all while ensuring that the desired number of Pods is consistently maintained. Kubernetes objects, including Deployments, are typically defined and configured using YAML files, often referred to as manifests.

You can view the `deployment.yml` file present in the project folder or copy it from here.

```bash
apiVersion: apps/v1
kind: Deployment
metadata:
  name: reddit-clone-deployment
  labels:
    app: reddit-clone
spec:
  replicas: 2
  selector:
    matchLabels:
      app: reddit-clone
  template:
    metadata:
      labels:
        app: reddit-clone
    spec:
      containers:
      - name: reddit-clone
        image: <username>/reddit-clone:latest
        ports:
        - containerPort: 3000
```

Make sure to replace the value of `image` key with that of your image name as shown in the YAML file.

The deployment creates 2 pods running 1 container each with the reddit-clone image we pushed earlier. The key **containerPort** declares that the container accepts connections from port 3000.

Run `kubectl apply -f deployment.yml` to create the deployment object in K8s. You should see an output similar to this:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694262269393/6c44dd67-2f93-4215-b84f-d0ed1487078d.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694262280295/45de8e63-eb91-438c-8194-aec1efdf140c.png align="center")

---

## **Step 7: Create a Service Manifest for K8s**

Our next step involves creating a Service object, which plays a vital role in enabling connectivity to the pods generated by the deployment configuration.

In Kubernetes (often abbreviated as K8s), a Service serves as a bridge connecting different pods or microservices within the cluster. Think of it as a well-known phone number in a directory that allows pods to establish connections and communicate with one another, even as their IP addresses change dynamically. Services are of utmost importance because they provide a stable and discoverable endpoint for applications. They also offer features like load balancing and abstraction of underlying pod modifications. This is especially valuable given Kubernetes' dynamic and scalable nature, as it would be challenging for pods to identify and interact with each other without the assistance of Services.

You can view the `service.yml` file present in the project folder or copy the one below and paste it into your YAML file

```bash
apiVersion: v1
kind: Service
metadata:
  name: reddit-clone-service
  labels:
    app: reddit-clone
spec:
  type: NodePort
  ports:
  - port: 3000
    targetPort: 3000
    nodePort: 31000
  selector:
    app: reddit-clone
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694262429106/093b95d4-7232-4710-a38e-0d521366a6c4.png align="center")

# **Step 8 Test your application**

Now it is time to test our deployed application. Since our service object is of the type ClusterIP, it is not accessible outside the cluster, but for the purpose of testing, we can forward all requests received in a specific port on the host to the service port using `kubectl port-forward` command.

Make sure port 3000 is not blocked by a firewall or a security group if you are running Linux on the cloud, This is crucial for testing the app.

You need to note the IP of the machine Minikube is running in, use `ifconfig` command on Linux to find your machine’s IP address.

Run the command `kubectl port-forward svc/reddit-clone-service 3000:3000 --address 0.0.0.0` After running this command, keep the terminal open.

Now in your browser, open the URL `<LinuxIP>:3000` Replace the placeholder `<LinuxIP>` with the IP of the Linux machine you noted above. If everything is configured well, you should see a site similar to this:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694262592927/b7359122-7d4c-434e-bdee-cebedb7aa95f.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694262681630/94a8dc5f-e26c-40ce-8105-552dc79eaaed.png align="center")

---

## **Step 9: Configuring Ingress**

**Ingress** is a clever traffic management and routing solution for Kubernetes apps running within the cluster. While **LoadBalancer** and **NodePort** Services are useful for exposing specific services, Ingress offers a more advanced solution. It serves as a **single entry point** for various services, making it an excellent solution when you need to access numerous microservices **via distinct URLs or domains**.

In Minikube, ingress comes as an addon and we need to enable it before configuring it. Run `minikube addons enable ingress` in the terminal to enable ingress. The output should be like this

### **Let's Write the Ingress K8s Manifest**

You can use the `ingress.yml` present in the project folder or copy the YAML from here:

```bash
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: ingress-reddit-app
spec:
  rules:
  - host: "domain.com"
    http:
      paths:
      - pathType: Prefix
        path: "/test"
        backend:
          service:
            name: reddit-clone-service
            port:
              number: 3000
  - host: "*.domain.com"
    http:
      paths:
      - pathType: Prefix
        path: "/test"
        backend:
          service:
            name: reddit-clone-service
            port:
              number: 3000
```

We have used the domain [**redditclone.com**](http://redditclone.com) as our entry point to the ingress Create the ingress rule using the command `kubectl apply -f ingress.yml`

# **Test Ingress**

We have now successfully deployed the ingress and now we can test it. To test the ingress, we need to send a request to [`redditclone.com`](http://redditclone.com) , however, we don’t own this domain, and there’s no DNS record pointing [**redditclone.com**](http://redditclone.com) to our cluster. So, we will be using curl command to forcefully resolve [**redditclone.com**](http://redditclone.com) to the IP of ingress as noted above. The command is:

```bash
curl --resolve "redditclone.com:80:<IP of Ingress>" redditclone.com
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694262827859/3e1c9d5c-b60d-44a7-96ef-4f0417cd0159.png align="center")

---

### Congratulations on the successful deployment of your Reddit clone!

Congratulations on your successful deployment of the Reddit clone application using Minikube! You've now opened the door to the world of Kubernetes, and this is just the start of your journey. Keep exploring, learning, and building with Kubernetes, as it offers limitless opportunities.

Thank you to all fellow Kubernetes enthusiasts. Feel free to follow me for more exciting blogs on Kubernetes, Docker, and Linux.