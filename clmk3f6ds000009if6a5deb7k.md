---
title: "Day 5 of #TerraWeek - Terraform Modules"
datePublished: Fri Sep 15 2023 04:22:07 GMT+0000 (Coordinated Universal Time)
cuid: clmk3f6ds000009if6a5deb7k
slug: day-5-of-terraweek-terraform-modules
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1694751700091/25090d54-4c93-4184-afef-a36633e9cb8d.jpeg
tags: devops, trainwithshubham, devopscommunity, trainwithshubham-techwithankush-seekhoaursikhao-twscommunitybuilders-90daysofdevops-connections-growth-community-learning-linkedin-devops-awsdevops-awscloud-awscommunity-aws-docker-dockercontainer-dockerhub-kubernetescluster-kubernetesservices-kubernetes-jenkins-ansible-ansibleautomates-linuxsystemadministration-linuxfoundation-linux-git-github-terraform-grafana-prometheus-cicd-cicdpipelines

---

## **Introduction**

In this post, we will explore the concept of Terraform modules, their benefits, how to create and use modules to encapsulate reusable infrastructure configuration and explain module composition and versioning.

---

### **Understanding Terraform Modules**

Terraform modules are self-contained packages of Terraform configurations that encapsulate a set of resources and their dependencies. Modules allow you to create reusable infrastructure components that can be shared across multiple projects or environments. By using modules, you can simplify your Terraform code, improve maintainability, and promote best practices.

To create a Terraform module, you typically organize your code into a directory with a specific structure. Here's an example of a <mark>basic module structure</mark>:

1. **Abstraction and Encapsulation**: Modules allow you to encapsulate a set of related resources and configurations into a single, reusable unit.
    
2. **Reusability**: Modules can be reused across multiple Terraform projects and configurations.
    
3. **Separation of Concerns**: Modules promote separation of concerns by breaking down complex infrastructure into smaller, manageable pieces.
    
4. **Versioning**: Modules can be versioned and published, allowing teams to use specific versions of modules in their configurations.
    
5. **Collaboration**: Modules facilitate collaboration among team members. Different team members can work on separate modules, and these modules can be integrated into a larger infrastructure configuration.
    
6. **DRY (Don't Repeat Yourself) Principle**: Modules encourage the DRY principle by eliminating the need to duplicate infrastructure code.
    

```abap
module/
  ├── main.tf
  ├── variables.tf
  └── outputs.tf
```

### Task 2 : **Creating and Using Terraform Modules**

To create a Terraform module, you'll need to create a new directory containing a set of **<mark>.tf</mark>** files that define the resources and variables for your module. Here's an example of a simple module that creates an AWS S3 bucket:

```abap
resource "aws_s3_bucket" "my_bucket" {
  bucket = var.bucket_name
  acl    = var.acl
}

variable "bucket_name" {
  description = "The name of your S3 bucket"
  type        = string
}

variable "acl" {
  description = "The access control list for the S3 bucket"
  type        = string
  default     = "private"
}
```

To use this module in your Terraform configuration, you'll need to add a **<mark>module block</mark>** that references the module's directory:

[**main.tf**](http://main.tf)**:**

```abap
provider "aws" {
  region = "us-east-1"
}

module "s3_bucket" {
  source      = "./modules/s3_bucket"
  bucket_name = "my-demo_123-bucket"
}
```

---

### Task 3 : **Module Versioning**

Terraform modules support versioning, allowing you to track changes to your modules over time and roll back to previous versions if needed. To version your modules, you can use a version control system like Git and tag your module releases with semantic versioning.

To reference a specific version of a module in your Terraform configuration, you can use the **version** argument in the **module** block:

```abap
provider "aws" {
  region = "us-east-1"
}
module "s3_bucket" {
  source      = "git::https://example.com/your-repo.git?ref=v1.0.0"
  bucket_name = "my-example-bucket"
}
```

Terraform uses a versioning scheme called <mark>Semantic Versioning</mark> (SemVer) to manage module versions. SemVer consists of three components: MAJOR, MINOR, and PATCH.

* **<mark>MAJOR</mark>** version increment indicates incompatible changes. This means there might be breaking changes in the module, and you may need to update your configuration to use the new version.
    
* **<mark>MINOR</mark>** version increment adds new features or functionality to the module but maintains backward compatibility. You can safely update to a new minor version without expecting any breaking changes.
    
* **<mark>PATCH</mark>** version increment includes backward-compatible bug fixes or patches. These updates address issues without introducing any new features or breaking changes.
    

To specify a module version in your Terraform configuration, you can use the `source` attribute along with the version constraint. Here are a few examples:

* Exact version constraint:
    

```abap
  module "example" {
    source  = "github.com/example/module?ref=v1.2.3"
    # ...
  }
```

Version constraint range:

```abap
  module "example" {
    source  = "github.com/example/module?ref=1.2.*"
    # ...
  }
```

Latest version constraint:

```abap
  module "example" {
    source  = "github.com/example/module?ref=latest"
    # ...
  }
```

---

## **Conclusion:**

Terraform modules are a powerful feature that enables you to create reusable infrastructure components and promote code reusability and maintainability. By understanding the concept of Terraform modules, learning how to create and use them, and exploring module composition and versioning, you can build modular and scalable infrastructure components that can be easily managed and updated. This will help you create more efficient and maintainable Terraform configurations.

The above information is up to my understanding. Suggestions are always welcome.

#terraform #terraform module #module versoning #aws #DevOps #TrainWithShubham #TerraWeekChallenge

#90daysofdevopsc #happylearning

@[Shubham Londhe](@TrainWithShubham) **Sir**

<mark>Follow for many such contents:</mark>

<mark>LinkedIn: </mark> [https://www.linkedin.com/in/vedant-adhe-4683b0192/](https://www.linkedin.com/in/vedant-adhe-4683b0192/)

<mark>Github</mark>:[https://github.com/VedantAdhe](https://github.com/VedantAdhe)