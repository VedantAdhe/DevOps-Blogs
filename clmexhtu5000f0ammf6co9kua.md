---
title: "Day - 2 of #TerraWeek  Terraform Configuration Language (HCL)"
datePublished: Mon Sep 11 2023 13:37:23 GMT+0000 (Coordinated Universal Time)
cuid: clmexhtu5000f0ammf6co9kua
slug: day-2-of-terraweek-terraform-configuration-language-hcl-1
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1694439375961/536ce180-434f-44cb-9a20-ebadb40da3b1.jpeg
tags: devops, trainwithshubham, devopscommunity, terraweekchallenge, trainwithshubham-techwithankush-seekhoaursikhao-twscommunitybuilders-90daysofdevops-connections-growth-community-learning-linkedin-devops-awsdevops-awscloud-awscommunity-aws-docker-dockercontainer-dockerhub-kubernetescluster-kubernetesservices-kubernetes-jenkins-ansible-ansibleautomates-linuxsystemadministration-linuxfoundation-linux-git-github-terraform-grafana-prometheus-cicd-cicdpipelines

---

---

## **Introduction:**

Welcome to this comprehensive guide on the HashiCorp Configuration Language (HCL), with a focus on its application in Terraform. In this blog post, we will delve into the intricacies of HCL syntax and equip you with the knowledge to craft effective Terraform configurations using this powerful language. Additionally, we will explore the nuances of variables, data types, and expressions within HCL, and provide insights into best practices for testing and debugging your Terraform configurations.

---

### **Why Use HCL in Terraform?**

Terraform employs HCL as its primary configuration language due to its simplicity and readability. HCL allows infrastructure engineers and DevOps professionals to define and manage cloud resources, servers, and other infrastructure components using a declarative approach. This means you describe **what** you want, and Terraform takes care of the **how**.

---

## **HCL Syntax**

HCL, short for HashiCorp Configuration Language, serves as the language that Terraform uses for expressing infrastructure configurations. It's designed to be straightforward for humans to read and write. With HCL, you can describe your infrastructure resources and data sources in a clear and declarative manner.

---

## **Understanding HCL Blocks**

In HCL, blocks are fundamental structural elements used to define various components within a configuration. Each block encapsulates a specific resource, module, or variable declaration. Blocks are often delimited by curly braces `{}` and contain key-value pairs that configure the associated element.

Here's a basic example of an HCL block that defines an AWS EC2 instance:

```abap
resource "aws_instance" "my-aws-instance" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"
}
```

In this example:

* `resource` is the type of <mark>block</mark>, specifying that we're defining a resource.
    
* `"aws_instance"` is the block type, indicating an AWS EC2 instance.
    
* `"my-aws-instance"` is a unique identifier (label) for this specific instance of the resource. It is used to reference this instance elsewhere in the configuration.
    

---

## **Parameters and Arguments**

Within HCL blocks, you use parameters and arguments to configure the associated resource or element. These parameters are essentially the keys, and their corresponding values are the arguments. Here's how it works:

* **Parameters**: Parameters are predefined by the resource type and specify what aspects of the resource you can configure. They are fixed and cannot be changed.
    
* **Arguments**: Arguments are user-defined values assigned to parameters. You provide arguments to configure the resource according to your specific needs. Arguments are flexible and can vary from one instance of a resource to another.
    

Continuing with our AWS EC2 instance example, let's break down the parameters and arguments:

Parameters, **ami** and **instance\_type** are the <mark>parameters</mark>,

Arguments: **"ami-0c55b159cbgjg6c52g4"** and **"t2.micro"** are the <mark>arguments</mark>.

---

## **Variables, Data Types and Expressions**

---

## **Variables in HCL**

Variables are a crucial component of Terraform configurations, serving as placeholders for storing and reusing values throughout your configuration. Defined using the variable block in HCL, they enhance the flexibility and dynamism of your configurations by centralizing the management of values, enabling convenient changes when needed.

To define a variable, create a [**<mark>variable. tf</mark>**](http://variable.tf) **file and add the following code:**

For example, you can define a variable for an AWS region like this:

```abap
variable "aws_region" {
  type    = string
  default = "us-east-1"
}
```

Here, we've created a variable named `"aws_region"` with a data type of `string`, and we've given it a default value of `"us-east-1"`. You can then use this variable throughout your configuration to reference the AWS region.

---

## **Data Types in HCL**

Data types in HCL specify the kind of data that a variable can hold. Common data types in HCL include:

* `string`: Represents text or <mark>characters</mark>.
    
* `number`: Represents numeric <mark>values</mark>, both <mark>integers</mark> and <mark>floating-point numbers</mark>.
    
* `bool`: Represents <mark>Boolean</mark> values (`true` or `false`).
    
* `list`: Represents an ordered <mark>collection</mark> of values of the same or different data types.
    
* `map`: Represents a collection of <mark>key-value pairs</mark>.
    

You specify the data type of a variable when you define it, ensuring that the variable holds the appropriate kind of data.

---

## **Expressions in HCL**

Expressions in HCL allow you to perform operations, <mark>calculations</mark>, and <mark>evaluations </mark> within your <mark>configurations</mark>. They enable you to make <mark>decisions</mark>, <mark>manipulate data</mark>, and create <mark>dynamic configurations</mark>.

For instance, you can use an expression to conditionally set the instance type of an AWS EC2 instance based on a variable:

```abap
resource "aws_instance" "example" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = var.use_small_instance ? "t2.micro" : "t2.medium"
}
```

In this example, `var.use_small_instance` is a variable representing a <mark>Boolean value</mark>. The expression `var.use_small_instance ? "t2.micro" : "t2.medium"` evaluates to `"t2.micro"` if the variable is `true` and `"t2.medium"` if it's `false`

---

## Practice writing Terraform configurations using HCL syntax

1. **Open or create your Terraform configuration file, typically named** [`main. tf`](http://main.tf)**.**
    
2. **Declare the** `required_providers` **block at the beginning of your configuration file.**
    
    For AWS as an example:
    
    ```abap
    terraform {
      required_providers {
        aws = {
          source = "hashicorp/aws"
          version = "~> 3.0"
        }
      }
    }
    ```
    
    In this example:
    
    * `required_providers` specifies that you are specifying a required provider.
        
    * `aws` is the name of the provider you are specifying.
        
    * `source` specifies the source of the provider. In this case, it's the official HashiCorp AWS provider.
        
    * `version` specifies the version constraints for the provider. The `~> 3.0` constraint means you want to use any version that is at least version 3.0 but less than version 4
        
3. You can similarly add the `required_providers` block for Docker or any other provider you intend to use, following the same format but replacing `aws` with the appropriate provider name and providing the corresponding source and version.
    
    For Docker as an example:
    
    ```abap
    terraform {
      required_providers {
        docker = {
          source = "terraform-providers/docker"
          version = "~> 2.0"
        }
      }
    }
    ```
    
4. **Save your** [`main.tf`](http://main.tf) **file.**
    

Now your Terraform configuration is set up to use the required providers (in this case, AWS and Docker). When you run `terraform init`, Terraform will automatically download and configure the specified providers based on the information provided in the `required_providers` block.

---

### **Testing and Debugging**

Testing and debugging Terraform configurations is a critical aspect of the development process. Here are some valuable tips and best practices to enhance your testing and debugging efforts

1. **<mark>Preview Changes</mark>:** Utilize the `terraform plan` command to gain insight into the changes Terraform intends to make before applying them. This helps you understand the impact of your configuration alterations without making actual modifications to your infrastructure.
    
2. **<mark>Apply Changes Safely</mark>:** Use the `terraform apply` the command to apply changes to your infrastructure. Always exercise caution when applying changes in production environments, and thoroughly review the plan before confirming the application.
    
3. **<mark>Resource Cleanup</mark>:** When you no longer need resources created by your configuration, employ the `terraform destroy` command to safely remove them. This helps prevent unnecessary costs and resource clutter.
    
4. **<mark>State Inspection</mark>:** The `terraform state` command is a valuable tool for examining the current state of your infrastructure. It provides detailed information about the resources Terraform manages, aiding in troubleshooting and debugging.
    
5. **<mark>Syntax Verification</mark>:** Prior to applying your configuration, run `terraform validate` to check for syntax errors or misconfigurations. This step ensures that your configuration adheres to the correct syntax and structure.
    
6. **<mark>Consistent Formatting</mark>:** Maintain code consistency and readability by using the `terraform fmt` command to automatically format your configuration files. Consistent formatting makes your code more accessible and manageable.
    
7. **<mark>Logging and Error Handling</mark>:** Implement robust logging and error-handling practices within your configurations. Utilize Terraform's logging features to capture essential information for diagnosing issues and debugging.
    
8. **<mark>Modularization</mark>:** If your configuration becomes complex, consider modularizing it into separate files or modules. This promotes reusability and simplifies debugging by isolating specific components.
    
9. **<mark>Testing Environments</mark>:** Create dedicated testing environments that mimic your production setup. This allows you to test configurations safely without impacting critical systems.
    
10. **<mark>Version Control</mark>:** Employ a version control system like Git to track changes to your Terraform code. This facilitates collaboration, rollback capabilities, and auditing of configuration modifications.
    

---

## **Conclusion:**

In this blog, we have delved into the fundamental aspects of HCL syntax, equipping you with the knowledge to craft robust Terraform configurations. We explored the intricacies of HCL, including its blocks, parameters, and arguments, which are the building blocks of infrastructure as code. Additionally, we dived into the realm of variables, data types, and expressions in HCL, understanding how these elements empower you to create dynamic and adaptable infrastructure configurations.

LinkedIn ([**https://www.linkedin.com/in/vedant-adhe-4683b0192/**](https://www.linkedin.com/in/vedant-adhe-4683b0192/))

GitHub ([**https://github.com/VedantAdhe**](https://github.com/VedantAdhe))