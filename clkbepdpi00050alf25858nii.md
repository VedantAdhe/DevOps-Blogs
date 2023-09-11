---
title: "Day - 05 of 90DaysofDevops"
datePublished: Thu Jul 20 2023 17:08:39 GMT+0000 (Coordinated Universal Time)
cuid: clkbepdpi00050alf25858nii
slug: day-05-of-90daysofdevops
tags: 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge, tws

---

## Day-05: Advanced Linux Shell Scripting for DevOps Engineers with User Management

### Introduction 💬

Welcome to the "Advanced Linux Shell Scripting for DevOps Engineers with User Management" course! In this comprehensive program, we'll dive into the exciting world of Linux Shell Scripting and learn how DevOps engineers can use powerful tools to streamline user management in a robust and secure environment.

For DevOps engineers, mastering Linux shell scripting is critical because it opens up a wide range of automation options that allow you to efficiently manage user accounts, permissions, and access rights on your systems. This course is designed to take your shell scripting skills to the next level and equip you with the knowledge and experience you need to confidently handle complex automation tasks.

Throughout this journey, you will gain an in-depth understanding of various shell scripting concepts, including variables, loops, conditions, functions, and more. You'll learn the power of command-line tools and how to use them to effectively manage users, groups, and permissions.

## Title: Automation of repetitive tasks with shell scripting

In the world of programming and automation, shell scripting has proven to be an indispensable tool for system administrators, developers and anyone who works with the command line. Thank you to its simplicity and power, it allows users to perform various tasks efficiently. In this blog, we will explore how shell scripting can be used to automate repetitive tasks by using loops and command line arguments, focusing specifically on a scenario involving start and end tag variables.

Scenario: Generate Daily Reports

Let us consider a scenario in which you work as an analyst for a company that generates daily reports on its sales data. Your task is to create a script that automatically generates reports for a specified number of days, from the start day to the end day. Instead of manually executing commands for each day, a shell script can make this process fast and error-free.

First steps

Before we start writing the script, make sure you have a basic knowledge of shell scripting and have access to a Unix-like terminal.

Step 1: Creating the script

Start by creating a new file called generate\_reports.sh. You can use any text editor you are familiar with such as Nano, vim, or Gedit.

```bash
#!/bin/bash

# Check if both start and end day arguments are provided
if [ "$#" -ne 2 ]; then
    echo "Usage: $0 <start_day> <end_day>"
    exit 1
fi

# Assigning arguments to variables
start_day=$1
end_day=$2


current_day=$start_day
while [ "$current_day" -le "$end_day" ]; do
  
    echo "Generating report for Day $current_day"
    
    # Increment Current DAy
    current_day=$((current_day + 1))
done
```

## **Step 2: Giving Executable Permission**

Next, give the script executable permission so that you can run it as a command.

```bash
chmod +x generate_reports.sh
```

### **Step 3: Running the Script**

Now, you can execute the script with your desired start and end days as arguments. For example:

```bash
./generate_reports.sh 1 7
```

This will generate reports for Day 1 to Day 7. You can modify the arguments as per your requirement.

### Implement dynamic directories:

Now that we understand the benefits, let us examine how to effectively implement dynamic directories:

1. Define the directory structure: first, define the structure you want to maintain. Consider the categories, subcategories, and rules that will govern the creation of directories. This structure will be the basis for your dynamic directories.
    
2. Choose a scripting language or programming environment: depending on your technical knowledge and the complexity of your requirements, choose an appropriate scripting language or programming environment. Python, for example, is a popular choice because of its ease of use and powerful file management libraries.
    
3. Capture metadata: If you want to create directories based on file attributes or metadata, make sure the files are tagged with the appropriate information. Metadata can include file type, creation date, author, or other relevant identifiers.
    
4. Develop the script or program: write a script or program that reads the files in the specified location and automatically creates directories based on the specified structure and rules. Incorporate error handling to resolve potential problems.
    
5. Test and refine: Before running the script on your entire file system, test it on a smaller sample to ensure that it behaves as expected. Refine the script as needed to account for unforeseen scenarios.
    
6. Back-up data: If you make major changes to your file system, be sure to back up your data to avoid accidental loss of files.
    
7. Schedule regular execution: Depending on your file management needs, you can have the script run at regular intervals (e.g., daily or weekly) to ensure continuous organization and customization of your directories.
    

### **Conclusion:**

Dynamic directories represent an advanced approach to file management that optimizes efficiency, organization, and productivity. By automating the process of directory creation and adapting to changing data requirements, you can free up valuable time and resources. Implementing dynamic directories requires an initial investment of time and effort, but the benefits it brings to your workflow and data organization are well worth it.

So leap into the world of dynamic directories and unlock the true potential of your file management capabilities. Rely on automation, scalability and consistency and experience a new level of efficiency in managing your digital assets. Have fun organizing!

I recently completed my Bachelor's degree in Computer Science/Information Technology, where I gained a solid foundation in DevOps. I also received comprehensive training in various aspects of DevOps methodologies, including continuous integration, continuous deployment, and infrastructure automation.

Stay connected with me for more interesting articles about Cloud and DevOps by following me on hashcode, LinkedIn ([**https://www.linkedin.com/in/vedant-adhe-4683b0192/**](https://www.linkedin.com/in/vedant-adhe-4683b0192/)) and GitHub ([**https://github.com/VedantAdhe**](https://github.com/VedantAdhe)) Connect [**Vedantadhe19@gmail.com**](mailto:Vedantadhe19@gmail.com)

Thank you for reading! Continue to support us, learn from each other and grow with us.