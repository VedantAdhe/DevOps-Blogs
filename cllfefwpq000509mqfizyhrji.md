---
title: "Day-15 For 90 Day's Of DevOps"
datePublished: Thu Aug 17 2023 16:52:04 GMT+0000 (Coordinated Universal Time)
cuid: cllfefwpq000509mqfizyhrji
slug: day-15-for-90-days-of-devops
tags: devops-articles, devops-jobs, devopscommunity, trainwithshubham-techwithankush-seekhoaursikhao-twscommunitybuilders-90daysofdevops-connections-growth-community-learning-linkedin-devops-awsdevops-awscloud-awscommunity-aws-docker-dockercontainer-dockerhub-kubernetescluster-kubernetesservices-kubernetes-jenkins-ansible-ansibleautomates-linuxsystemadministration-linuxfoundation-linux-git-github-terraform-grafana-prometheus-cicd-cicdpipelines

---

---

### Mastering DevOps with Python: Must-Have Libraries for Efficiency

1\. What is a JSON File?

1. What is a YAML file?
    
2. Create a Dictionary in Python and write it to a JSON File.
    
3. Read a JSON file services.json kept in this folder and print the service names of every cloud service provider.
    
4. Read YAML file using python file service.yml and read the contents to convert yml to json.
    

---

1. ### What is a JSON file?
    

* JSON stands for JavaScript Object Notation.
    
* JSON is easy for both humans to read and write and for machines to parse and generate.
    
* JSON is primarily used in web development for transmitting data between a server and a web application as an alternative to XML.
    
* JSON objects are enclosed in curly braces `{}`, and each key-value pair is separated by a colon `:`.
    
* JSON data is represented in key-value pairs, where the keys are strings, and the values can be of various data types, such as strings, numbers, booleans, arrays, and even other JSON objects.
    
* JSON values cannot be functions or methods; they are meant to be data only.
    
* JSON arrays are ordered lists of values, enclosed in square brackets `[]`, with each value separated by a commad .
    
* Python has numerous libraries like `os`, `sys`, `json`, `yaml` etc that a DevOps Engineer uses in day-to-day tasks.YAML stands for Yet Another Markup Language. It is used to write a configuration file for the applications.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692290559177/f6094c07-12a8-4a50-a686-045abd17e0cf.png align="center")

---

1. What is JSON File?
    

* YAML stands for Yet Another Markup Language. It is used to write a configuration file for the applications.
    
* Yaml is human readable data serialization language that is often used for writing the configuration file depending on whom you ask.
    
* It is easy to read and understand
    
* yaml file use a.yml or .yml extension. it supports JSON files.
    
    It is simple to use and in the Python style. in the 3 dashes (---) is used to signal the start of a document and (...) is used to end the documents.
    
* Yaml is used by the Ansible automation tool to create automation processes in the form of an Ansible playbook.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692290674872/cf3c53fd-3647-45b8-b6fb-4fe70115b1c7.png align="center")

---

1. ### **Create a Dictionary in Python and write it to a JSON File.**
    

```bash
import JSON 

#Create Dictionary 
data = {
    "name":"Vedant ",
    "age":24,
    "Hobbies": ["DevOps","Driving","Technology"]
}

#Writing to JSON file
with open(dump_data, "w") as jsonfile:
    json.dump(data, jsonfile)

#Printing message
print(f"Data has been converted into JSON file")
```

Here,

data, --&gt; is a python dictionary

with open(), --&gt; is a function to open a particular file and "w" is used to write in it.

json.dump(), --&gt; function used to write to a json file.

---

### **Read a JSON file** `services.json` kept in this folder and print the service names of every cloud service provider.

```bash
output

aws : ec2
azure : VM
gcp : compute 




import json

#Read json file
with open("services.json", "r") as jsonfile:
    cloud = json.load(jsonfile)

#Print cloud providers
print(f"aws :", cloud['services']['aws']['name'])
print(f"azure :", cloud['services']['azure']['name'])
print(f"gcp :", cloud['services']['gcp']['name'])
```

---

1. ### **Read YAML file using python, file** `services.yaml` and read the contents to convert YAML to JSON.
    

```bash
import yaml
import json

with open("services.yml", "r") as yaml_file:
    yaml_data = yaml.safe_load(yaml_file)
    print(type(yaml_data))

with open("myfile.json", "w") as json_file:
    jsd = json.dump(yaml_data, json_file)
    print(jsd)
```