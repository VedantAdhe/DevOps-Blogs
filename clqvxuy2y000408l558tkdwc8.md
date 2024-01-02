---
title: "Level Up Your EKS Cluster: Mastering the Game of Kubernetes"
datePublished: Tue Jan 02 2024 05:58:29 GMT+0000 (Coordinated Universal Time)
cuid: clqvxuy2y000408l558tkdwc8
slug: level-up-your-eks-cluster-mastering-the-game-of-kubernetes
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1704174917768/a11e5dec-f1d3-4f62-b3fa-70b3f7bcb226.jpeg
tags: devops, trending, eks-cluster, trainwithshubham, 2024, trainwithshubham-90daysofdevopschallenge-linux-opensource-technology-operatingsystem-90daysdevops-devopscommunity-devopsfodnahai-hiring-immediatejoiners-devopsengineer-cloudcomputing-cloudtechnology-continuousintegration-continuousdelivery-terraweek-community-twsstudentscholarship-developertools-linkedin-linuxcommands-shellscripting-scripting-awscommunity-awscommunityday-aws, vedops

---

Elastic Kubernetes Service (EKS) is the Kubernetes service managed by AWS. It is a managed service that helps simplify the deployment, management, and scaling of the Kubernetes cluster on the AWS cloud platform. It provides seamless integration with various AWS services like Cloud-Watch, VPC, and IAM, making it easier to utilize AWS resources which helps to improve performance, security, and scaling. This service follows the AWS pricing model where users only need to pay for the used resources required to manage the EKS cluster which helps to optimize pricing.

---

## **Follow these steps to set up the EKS cluster:**

Configure the EC2 instance which is going to be an entry point of our EKS cluster, you can use t2.micro(free tier) for that.

* Connect your instance using SSH to give commands and interact from your terminal.
    
* Do the pre-requisites with the newly launched instance `sudo apt update`
    

**Install AWS CLI:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704174488880/119a6c95-4862-49af-b540-a33292fc4e5d.png align="center")

```bash
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"

sudo apt install unzip

unzip awscliv2.zip

sudo ./aws/install -i /usr/local/aws-cli -b /usr/local/bin --update
```

* This command basically installs the aws cli which command line tool to interact with AWS.
    

You can confirm your installation with:

```bash
aws --version
```

---

### **Configure IAM User:**

* Configure your IAM user which will give you the access keys to connect with your AWS securely through the terminal and ensure that to have required specific permissions to create and use AWS resources and services.
    
* Navigate to the IAM settings and click on Create User.
    
* Give a suitable username to the IAM group.
    
* ***No need to check the box to provide access to the management console. and click on the next.***
    
    Set permissions as per the requirements to do so <mark>select Attach policies directly</mark>. In this example, I'm giving admin access.
    
* Now your user is created "<mark>eks-admin</mark>".
    
* Go to the security credentials and click on <mark>create credentials</mark>.
    
* Click on the <mark>Create Access key</mark>.
    
* Then you will see this interface which will give several types of options to create an access key.
    
* elect the <mark>Command Line Interface(CLI)</mark> option.
    
* Then <mark>check</mark> the box of <mark>confirmation</mark> and click next.
    
* On the next page, you can see the generated access keys.
    
* Now configure your ec2 instance with the IAM user you have created to give all required permissions to create an EKS cluster.
    
* Go to the terminal and type the command `aws configure`
    
* Then the terminal will ask you for <mark>credentials</mark> and <mark>region</mark>, and put in the generated credentials and region.
    

```bash
  aws configure
```

---

## **Now we are going to set up Kubernetes tools.**

### **Install Kubectl:**

```bash
curl -o kubectl https://amazon-eks.s3.us-west-2.amazonaws.com/1.19.6/2021-01-05/bin/linux/amd64/kubectl

chmod +x ./kubectl

sudo mv ./kubectl /usr/local/bin

kubectl version --short --client
```

Confirm your installation `kubectl version --short --client` with this command, you will get the output.

---

### **Install eksctl :**

```bash
curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp

sudo mv /tmp/eksctl /usr/local/bin

eksctl version
```

Confirm your installation `eksctl version` with this command, you will get the output: 0.165.0

**Now to create your cluster with this command:**

```bash
  eksctl create cluster --name 2-tier-app-cluster --region ap-south-1 --node-type t2.micro --nodes-min 2 --nodes-max 4
```

* It will take 15-20 minutes to create the cluster.
    

After successfully creating the cluster see the running nodes.

```bash
kubectl get nodes

You will see your EKS cluster is active.
```

You will see this output where you can see the running nodes.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704174385863/9b714c83-254e-4e5b-b747-3631762aea8c.jpeg align="center")

---

## **Destroying cluster:**

* It's easy to destroy clusters through the terminal if you are trying to destroy it from the console it's a bit difficult.
    
* Because the EKS cluster uses AWS's LoadBalancer service in the background
    
* So in case you terminated your entry point instance you will need to manually delete the load balancer service.
    
* So always use the command to destroy the cluster.
    
* A command for destroying cluster
    

```bash
  eksctl delete cluster --name 2-tier-app-cluster
```

---

I am a passionate DevOps enthusiast with a strong foundation in Linux, containerization, orchestration, automation, and cloud technologies. My goal is to continuously learn and implement DevOps best practices to streamline development and operations processes.

---

1. LinkedIn [linkedin.com/in/vedant-adhe](https://www.linkedin.com/in/vedant-adhe)
    
2. **GitHub (**[**github.com/VedantAdhe**](http://linkedin.com/in/vedant-adhe-4683b0192)**)**
    
3. **Connect** [**Vedantadhe04@gmail.com**](http://linkedin.com/in/vedant-adhe-4683b0192)
    

!!!!!Thank you for reading !!!!!