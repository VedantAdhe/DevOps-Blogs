---
title: "Day 3 of #TerraWeek - Managing Resources"
datePublished: Tue Sep 12 2023 12:59:58 GMT+0000 (Coordinated Universal Time)
cuid: clmgblkyc000i09mnbwxacfbh
slug: day-3-of-terraweek-managing-resources
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1694522754637/f8cf4e7c-d6e7-4486-b44d-373c27302876.jpeg
tags: trainwithshubham, devopscommunity, terraweekchallenge, trainwithshubham-techwithankush-seekhoaursikhao-twscommunitybuilders-90daysofdevops-connections-growth-community-learning-linkedin-devops-awsdevops-awscloud-awscommunity-aws-docker-dockercontainer-dockerhub-kubernetescluster-kubernetesservices-kubernetes-jenkins-ansible-ansibleautomates-linuxsystemadministration-linuxfoundation-linux-git-github-terraform-grafana-prometheus-cicd-cicdpipelines

---

## **Introduction:**

In this blog post, we will delve into the world of resource management with Terraform. Our focus will be on different resource types and their respective configurations, including AWS EC2 instances, Azure Virtual Machines, and Google Compute Engine instances. Additionally, we will explore topics like resource dependencies, provisioners, and lifecycle management.

---

### **Defining Resources with Terraform:**

In Terraform, to create a new infrastructure object, you use a "resource block." This block starts with the keyword "resource," followed by the specific "resource type" that defines the kind of infrastructure element you want to create. Additionally, you provide a "unique name" for the resource within your Terraform configuration. This unique name is used to identify and reference the resource throughout your Terraform configuration files.

```abap
resource "aws_instance" "my-ec2-instance" {
  ami           = "ami-08c40ec9ead489470"
  instance_type = "t2.micro"
}
```

In this example, we are setting up a virtual server on Amazon Web Services (AWS) using a service called EC2. We give this server a specific name, which is "my-ec2-instance." We also provide some important details to configure this server, such as the type of operating system image (ami) we want to use and the size and specifications of the server (instance\_type).

---

### **AWS EC2 Instance Configuration:**

```abap
# Define the provider (AWS in this case)
provider "aws" {
  region = "us-east-1" # Specify the AWS region you want to use
}

# Define the EC2 instance resource
resource "aws_instance" "example_instance" {
  ami           = "ami-0c55b159cbfafe1f0" # Replace with the desired AMI ID
  instance_type = "t2.micro"            # Specify the instance type

  # Define the security group for the instance
  vpc_security_group_ids = ["sg-0123456789abcdef0"] # Replace with your security group ID

  # Define the key pair for SSH access
  key_name = "your-key-pair-name" # Replace with your key pair name

  # Define user data if needed (e.g., for instance configuration scripts)
  user_data = <<-EOF
              #!/bin/bash
              echo "Hello, EC2 instance!"
              EOF

  # Define tags for the instance
  tags = {
    Name = "ExampleInstance"
  }
}
```

In this configuration:

1. We specify the AWS provider with the desired region.
    
2. We define an EC2 instance resource named "example\_instance." You can customize the `ami` (Amazon Machine Image), `instance_type` (instance size), `vpc_security_group_ids` (security group IDs), `key_name` (SSH key pair), `user_data` (startup script), and `tags` (metadata) according to your requirements.
    
3. Be sure to replace `"ami-0c55b159cbfafe1f0"` with the actual AMI ID you want to use and `"sg-0123456789abcdef0"` with your security group ID. Also, replace `"your-key-pair-name"` with your SSH key pair name.
    

To apply this configuration, save it to a file with a `.tf` extension (e.g., `ec2_instance.tf`), initialize your Terraform workspace with `terraform init`, and apply it with `terraform apply`. Make sure you have the AWS CLI configured with appropriate credentials or IAM roles.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694521632373/3b64395e-a26f-4c58-bd53-85f9217d3022.png align="center")

---

### Terraform commands:

1. **Check State Files**: Before making any changes to your infrastructure, it's crucial to check the state files to ensure they are up-to-date and reflect the current state of your infrastructure. Use the `terraform state list` command to list the resources currently managed by Terraform:
    
    ```abap
    terraform state list
    ```
    
    This command will list the resources Terraform is aware of and managing.
    
2. **Validate Terraform Configuration**: You should validate your Terraform configuration files for syntax errors and other issues before applying any changes. Use the `terraform validate` command for this:
    
    ```abap
     terraform validate
    ```
    
    This command will check your configuration files (usually with a `.tf` extension) for errors and provide feedback if any issues are found.
    
3. **Plan the Changes**: Once you've ensured that your state files are in order and your configuration is error-free, you can generate a plan to preview the changes Terraform will make. Use the `terraform plan` command:
    
    ```abap
    terraform plan
    ```
    
    This command will show you a summary of the changes Terraform intends to make to your infrastructure.
    
4. **Review the Plan**: Carefully review the plan to ensure it aligns with your expectations. It will display information about resource creation, modification, or destruction.
    
5. **Apply the Changes**: If you are satisfied with the plan and ready to apply the changes, execute the `terraform apply` command:
    
    ```abap
    terraform apply
    ```
    
    Terraform will ask for confirmation before proceeding. Type "yes" to apply the changes.
    
6. **Confirm and Monitor**: After applying the changes, review the output to ensure that Terraform successfully completed the desired actions. Monitor your infrastructure to ensure it is in the expected state.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694521955901/c812a947-7c26-428f-97fc-7bfdda4a21cd.png align="center")

---

### Configuration File:

To configure a resource after it is created using Terraform and then apply changes or destroy resources, you can use a provisioner. Provisioners in Terraform allow you to run scripts or commands on a resource after it's created. Here's a step-by-step guide on how to do this:

1. Open your Terraform configuration file (usually with a `.tf` extension) in a text editor.
    
2. Define the resource you want to create. For example, let's say you want to create an AWS EC2 instance:
    

```abap
resource "aws_instance" "example" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"
}
```

1. Add a provisioner block to the resource to configure it after creation. You can use the `remote-exec` provisioner to run remote commands on the instance:
    

```abap
resource "aws_instance" "example" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"

  provisioner "remote-exec" {
    inline = [
      "sudo apt-get update",
      "sudo apt-get install -y nginx",
    ]
  }
}
```

In this example, we're updating the package list and installing Nginx on the EC2 instance using inline commands.

1. Save the configuration file.
    
2. Open your terminal and navigate to the directory containing your Terraform configuration file.
    
3. Run the following commands to apply changes and create the resource:
    

```abap
terraform init
terraform apply
```

Terraform will initialize the project and then create the AWS EC2 instance. After the instance is created, the provisioner block will execute the specified commands.

1. To destroy the resources when you're done, run:
    

```abap
terraform destroy
```

Terraform will prompt you to confirm the destruction of the resources, and if you confirm, it will delete the resources, including the EC2 instance.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694522269899/cfd189b4-574b-4fdb-8ef4-d99236979480.png align="center")

---

### **Lifecycle Management:**

Terraform allows you to manage the lifecycle of resources using the **lifecycle** block. This block can be used to configure how Terraform should handle resource creation, updates, and destruction. Here's an example of using the **lifecycle** block to prevent the accidental destruction of an AWS EC2 instance:

**COPY**

```abap
resource "aws_instance" "my-instance" {
  ami           = "ami-0c94855ba95b798c7"
  instance_type = "t2.micro"

  lifecycle {
    prevent_destroy = true
  }
}
```

In this example, the **prevent\_destroy** argument is set to **true**, which means that Terraform will not allow the EC2 instance to be destroyed.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694522382145/e71d9f39-a3cc-4095-9b81-6c41b4bdd1f4.png align="center")

---

## **Conclusion:**

In this blog post, we've delved into the world of resource management with Terraform, putting the spotlight on different resource types and the ways to configure them. We've covered some of the heavy hitters like AWS EC2 instances, shedding light on how to set them up effectively. But we didn't stop there. We also took a closer look at the intricate dance of resource dependencies, which is like the backbone of orchestrating your infrastructure. We talked about provisioners, and the handy tools for fine-tuning your resources, and explored the art of lifecycle management, ensuring that your resources stay in harmony with your infrastructure needs. By gaining a solid grasp of these fundamental concepts, you're now armed with the knowledge and skills to be a Terraform maestro, capable of steering your cloud infrastructure with confidence and precision. Whether it's spinning up virtual machines or crafting complex cloud environments, Terraform has got your back, and you've got Terraform in your toolkit. So go forth and conquer the cloud!

---

LinkedIn ([**https://www.linkedin.com/in/vedant-adhe-4683b0192/**](https://www.linkedin.com/in/vedant-adhe-4683b0192/))

GitHub ([**https://github.com/VedantAdhe**](https://github.com/VedantAdhe))

---