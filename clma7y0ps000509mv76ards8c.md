---
title: "Kubernetes-Flask Deploy: Container Orchestration for Microservices"
seoDescription: "homepage illustrations"
datePublished: Fri Sep 08 2023 06:31:03 GMT+0000 (Coordinated Universal Time)
cuid: clma7y0ps000509mv76ards8c
slug: kubernetes-flask-deploy-container-orchestration-for-microservices
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1694154811523/c49389f4-f704-4ce2-a6cb-98c72fce67f3.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1694154605756/d78937d9-0737-43a6-9eb3-cb0b7c935979.png
tags: microservices, projects, kubernetes, kubeweekchallenge, trainwithshubham-techwithankush-seekhoaursikhao-twscommunitybuilders-90daysofdevops-connections-growth-community-learning-linkedin-devops-awsdevops-awscloud-awscommunity-aws-docker-dockercontainer-dockerhub-kubernetescluster-kubernetesservices-kubernetes-jenkins-ansible-ansibleautomates-linuxsystemadministration-linuxfoundation-linux-git-github-terraform-grafana-prometheus-cicd-cicdpipelines

---

Introduction Of Project

In the realm of modern container orchestration, Kubernetes emerges as a pivotal and indispensable tool, revolutionizing the deployment and management of microservice-based applications. This project endeavors to showcase the seamless integration of Kubernetes with a Flask microservice application, unveiling a symphony of containerization, scalability, and automation.

Employing Kubernetes as the orchestrator of choice, this initiative navigates the intricate terrain of containerized microservices, leveraging its dynamic scheduling, load balancing, and self-healing capabilities. By harnessing Kubernetes' declarative configuration and service discovery prowess, we empower the Flask application to transcend traditional deployment constraints, ensuring resilience and responsiveness in the face of varying workloads.

Key elements of this endeavor encompass the creation of Kubernetes pods, replication controllers, and services to encapsulate and scale the Flask microservices. Through containerization, we isolate application components, fostering modularity and flexibility while enabling efficient resource allocation.

Furthermore, this project explores the intricacies of Kubernetes' rolling updates and version management, enabling the smooth transition between application revisions, all without service disruption. Monitoring and logging mechanisms, orchestrated through Kubernetes, are harnessed to maintain visibility and troubleshoot performance issues, ensuring robustness in the microservices ecosystem.

In summary, this project serves as a testament to Kubernetes' prowess as an orchestrator, demonstrating its pivotal role in the deployment and management of a Flask microservice application. Through its dynamic orchestration and automation capabilities, Kubernetes elevates the deployment process to new heights, redefining the paradigm of containerized microservices in the ever-evolving landscape of modern software architecture.

---

### Let's Get Started with Deploying Microservices on Kubernetes.

### Phase 1

I began the project by launching two AWS EC2 instances with the following specifications:

* Operating System: Ubuntu (Xenial or a later version)
    
* User with sudo privileges
    
* Internet access
    
* Instance Type: t2.medium
    

After creating the instances, I designated one of them as the "Master Node" and established an SSH connection to that instance. Upon accessing the shell, the initial step was to update the machine by executing the following command:

```bash
sudo apt update
```

Next Step to Install the Certificates.

```bash
sudo apt-get install -y apt-transport-https ca-certificates curl
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694152595762/d10d7210-d89a-40e9-8fb8-d3f0115811df.png align="center")

The next Step To install Docker to Ensure for build and Deploy Images

```bash
sudo spt install Docker.io
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694151375159/4a1597f0-8438-4f2d-a9d2-263b3d2077a7.png align="center")

Enable The Service and Start the Docker service

```bash
sudo systemctl enable --now docker
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694151473611/8307165b-4563-45a1-aaba-5259d302af28.png align="center")

Once we start enabling the docker service, it's time to add the GPG keys

```bash
curl -fsSL "https://packages.cloud.google.com/apt/doc/apt-key.gpg" | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/kubernetes-archive-keyring.gpg 
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694151569090/d3f9a6ad-2d54-4faf-8fce-5d53168cc26e.png align="center")

Post the Addition of the GPG Keys, it is time to add the repository to the Source list

```bash
echo 'deb https://packages.cloud.google.com/apt kubernetes-xenial main' | sudo tee /etc/apt/sources.list.d/kubernetes.list
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694151670127/991fb849-565a-40d1-9cc2-fe54ac657983.png align="center")

Once all this has been completed, we need to update the system

```bash
sudo apt update
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694151704020/1e2f9c8c-294d-4c09-b748-2f6ba3060fb1.png align="center")

```bash
Once the system updates, it's time to install kubeadm

sudo apt install kubeadm=1.20.0-00 kubectl=1.20.0-00 kubelet=1.20.0-00 -y
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694151754577/9606f168-58c8-470d-9d08-e86c8eea880a.png align="center")

```bash
Initiate the kubeadm mode using the below command

sudo kubeadm init
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694151867079/d1e67062-f7c3-4d96-a043-5e8e84613b8e.png align="center")

Once this completes, you should be able to see the message that control-plane has initialized successfully.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694151895321/fc8c9e95-0f74-40bb-aeec-e91acdcff6b1.png align="center")

We can use the export command highlighted to export the configuration so that it can be reused in case of requirements.

The next steps are to create a folder called kube and then copy the configuration over and change the ownership of this file.

Run the set of commands from the previous output to perform the actions mentioned above.

```bash
mkdir -p $HOME/.kube

sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config

sudo chown $(id -u):$(id -g) $HOME/.kube/config

or

export KUBECONFIG=/etc/kubernetes/admin.conf
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694152054951/80b00113-3aa1-492e-9013-ed21dd01eed4.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694152173172/4145b209-281c-451e-bea4-0c6f36c87db2.png align="center")

```bash
Next two steps are to create a CNI using the weave-net and to generate a join token:

kubectl apply -f https://github.com/weaveworks/weave/releases/download/v2.8.1/weave-daemonset-k8s.yaml

sudo kubeadm token create --print-join-command
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694152249475/c824acf0-7a76-42a8-ac28-2b6de6da48a7.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694152269310/4ef3fdbe-22de-4586-a6af-8c79f8a2da2e.png align="center")

```bash
Just to confirm write this command

kubectl get nodes
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694152376857/38e63aaa-ce65-46c8-b518-31c33231accf.png align="center")

---

### Now Let's Setup Worker Node

Update the Worker Node instance again

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694152486097/8575d3f9-b0cf-432a-8885-242bf34328bc.png align="center")

Install Docker

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694152696931/a5c9483d-a8ed-4baf-853d-f1d2439a24a9.png align="center")

Start and Enable Docker

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694152769491/6aad6f70-e6ff-454f-8666-d931b80d0cbf.png align="center")

Add the GPG keys

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694152835286/8a01d399-4cd9-45d1-b1a5-9e989d96b657.png align="center")

Add the repository to the source

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694152874660/d0b13574-de32-4415-9daf-72010f398e1b.png align="center")

Update the instance again

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694152896738/149b9a61-7c08-49f0-b40e-453df42d1a09.png align="center")

The next step is to reset the pre-flight checks. This is a precautionary step done to ensure that if the init has been performed, it will be reset.

Run the command below to execute the task:

```bash
sudo kubeadm reset pre-flight checks
```

The last step of phase 1 is to join the worker node to the master. Use the join statement output that we got from the master node. Also, add --v=5 at the end. Execute the command below to get this task done (This command is specific to the instance you create so make sure to copy one from your instance)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694153148478/e8e85013-5bd5-41a0-a0d7-0f060b044cdf.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694153190825/5c34d170-7ede-45ff-8b9a-6e90e4657bf7.png align="center")

Phase 2 Let's Create a YML file Needed to Deploy the App

Fork the [**Git repository**](https://github.com/LondheShubham153/microservices-k8s.git) for all the necessary files.

Once you fork this repo, clone it to your master node (note that the prerequisite here is the master node must have the git installed, if you would like, as an additional step, execute)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694153346550/09535618-8666-4b38-afaa-d933c1642df7.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694153378033/2c46039f-7fba-4cc4-9124-2369cc94095c.png align="center")

Once you clone the repo, navigate to the folder containing the yml files and apply all the configurations:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694153412000/cc2366f9-694f-4dfb-bab4-8a8a1f0eb499.png align="center")

```bash
Lets delpoy the taskmaster yml file
kubectl apply -f taskmaster.yml
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694153501220/e2c69197-78da-4277-989f-b687b1c9565e.png align="center")

```bash

Lets delpoy the taskmaster Service  yml file 
kubectl apply -f taskmaster.yml
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694153551542/429163ac-89b2-4051-a960-f68279092289.png align="center")

```bash
Lets delpoy the Mongo  yml file 
kubectl apply -f mongo.yml
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694153615076/b669196f-740e-427a-a262-4574666bb6e0.png align="center")

```bash
Lets delpoy the Mongo Service file for Database yml file 
kubectl apply -f mongo-svc.yml
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694153626694/6032b246-ac6f-4c20-b5ca-b33dd6157cd4.png align="center")

```bash
Lets delpoy the mongo pv yml file 
kubectl apply -f mongo-pv.yml
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694153634565/95888032-db2e-4ac2-9d63-baad35a98a62.png align="center")

```bash
Lets delpoy the mongo pvc yml file 
kubectl apply -f mongo-pvc.yml
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694153656766/5b083f26-db49-407d-9470-ef41849e2f2f.png align="center")

```bash
To verify the deployment's success, execute the command below:

kubectl get deployments,services
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694153693632/8a9ed800-f824-46e2-bbe2-837315224f4e.png align="center")

---

### Phase - 3 is the Deployment of App

Now that we have deployed all the necessary files and the app is ready to be tested, run the curl command to test the deployment.

```bash
curl http://<service-ip>:<service-port>
```

Service IP is nothing but the public IP of the master node and the port that has been assigned for the application. In my case the application is hosted on the EC2 instance with the public IP 3.21.242.206 and the port 30007. So the command (in my case) is:

curl [**http://54.90.76.243:30007**](http://3.21.242.206:30007)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694154173391/67bfd22d-be57-4515-b86e-4c988dbcc300.jpeg align="center")

To test the microservices run **curl** [**54.90.76.243:30007/tasks**](http://3.21.242.206:30007/tasks)

This should also give you an output that the **"Task was saved successfully!"**

That's all folks! There we have it! An application that is based on microservices architecture deployed using Kubernetes.

I would love to hear back on how was this project executed and if there is any scope for improvements!

Happy learning!