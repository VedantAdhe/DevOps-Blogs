---
title: "Day-14 For 90 Day's Of DevOps"
datePublished: Wed Aug 16 2023 14:52:03 GMT+0000 (Coordinated Universal Time)
cuid: cllduppqj000408le6npkdc19
slug: day-14-for-90-days-of-devops
tags: devops-articles, devops-journey, 90daysofdevops, trainwithshubham, devopsjobs

---

### Python for DevOps: Building a Strong Foundation with Data Types and Structures

---

1. List
    
2. Tuple
    
3. Dictionary
    
4. Set
    
5. Create the below Dictionary and use the Dictionary method to print your favorite tool just by using the keys of the Dictionary
    
6. Create a list of cloud service providers Write a program to add Digital Ocean to the list of cloud\_providers and sort the list in alphabetical order.
    

---

## List :

* Lists are used to store data of different data types sequentially.
    
* The index value starts from 0 and goes on until the last element called the positive index
    
* There is also negative indexing which starts from -1 enabling you to access elements from the last to the first.
    
* Lists can contain duplicate elements.
    
* Lists are mutable, meaning you can add, remove, or modify elements after creation.
    
* Elements in a list are enclosed in square brackets `[ ]`.
    

Note:

* Lists are ordered and allow duplicates. They are mutable, so you can modify them after creation.
    

### **Hands-on Example for List:**

```bash
#creating a List
fruits_List=["Apple","Orange","Apple","Grapes"]

# Modifying the list
fruits_list[0] = "watermelon"
fruits_list.append("Mango")

# Displaying the list
print(fruits_list)
```

Output:

```bash
['watermelon','Banana','Orange','Apple','Grapes','Mango']
```

---

## Tuple:

Tuples are the same as lists are with the exception that the data once entered into the tuple cannot be changed no matter what. The only exception is when the data inside the tuple is mutable, only then the tuple data can be changed.

```bash
# Creating a tuple
fruits_tuple = ("apple", "banana", "orange", "apple", "grape")

# Trying to modify the tuple (will raise an error)
# fruits_tuple[0] = "watermelon"

# Displaying the tuple
print(fruits_tuple)
```

Output:

```bash
('apple', 'banana', 'orange', 'apple', 'grape')
```

Note:

* Tuples are ordered and allow duplicates. However, they are immutable, so you cannot change their elements after creation.
    

---

## Set:

Sets are a collection of unordered elements that are unique. Meaning that even if the data is repeated more than one time, it would be entered into the set only once. It resembles the sets that you have learned in arithmetic. The operations also are the same as are with the arithmetic sets.

```bash
# Creating a set
fruits_set = {"apple", "banana", "orange", "apple", "grape"}

# Adding elements to the set
fruits_set.add("watermelon")

# Displaying the set
print(fruits_set)
```

Output:

```bash
{'watermelon', 'banana', 'apple', 'grape', 'orange'}
```

In the example, we create a set of fruits, and you can see that duplicate elements are automatically removed from the set. We also add "kiwi" to the set.

Note:

* Sets are unordered and do not allow duplicates. They are mutable, so you can add or remove elements after creation.
    

---

## Task 1:

## **Create the below Dictionary and use Dictionary methods to print your favorite tool just by using the keys of the Dictionary**

```bash
fav_tools = {
    1: "Linux",
    2: "Git",
    3: "Docker",
    4: "Kubernetes",
    5: "Terraform",
    6: "Ansible",
    7: "Chef"
}

# Ask the user to enter the key
user_key = int(input("Enter the key of your favorite tool (1-7): "))

# Use dictionary method to retrieve the value
favorite_tool = fav_tools.get(user_key)

# Check if the key exists in the dictionary
if favorite_tool is not None:
    print(f"Your favorite tool is: {favorite_tool}")
else:
    print("Invalid key. Please enter a key between 1 and 7.")
```

In this script, the user is prompted to enter a key (1 through 7) that corresponds to their preferred tool. The get() method is then used to retrieve the value associated with the key entered from the fav\_tools dictionary. If the key exists, the preferred tool is printed, otherwise an error message for an invalid key is displayed.

If you run the script and enter a valid key, it prints your preferred tool based on the entered key. For example:

```bash
Enter the key of your favorite tool (1-7): 3
Your favorite tool is: Docker
```

If you enter an invalid key it will show the error message

```bash
Enter the key of your favorite tool (1-7): 8
Invalid key. Please enter a key between 1 and 7.
```

---

## **Create a List of cloud service providers Write a program to add** `Digital Ocean` to the list of cloud\_providers and sort the list in alphabetical order.

```bash
cloud_providers = ["AWS", "GCP", "Azure"]
```

```bash
cloud_providers = ["AWS", "GCP", "Azure"]

# Adding "Digital Ocean" to the list
cloud_providers.append("Digital Ocean")

# Sorting the list in alphabetical order
cloud_providers.sort()

# Displaying the updated list
print("Updated List of Cloud Providers:")
for provider in cloud_providers:
    print(provider)
```

When you run this script, it adds "Digital Ocean" to the list and sorts them in alphabetical order:

```bash
Updated List of Cloud Providers:
AWS
Azure
Digital Ocean
GCP
```

Now, the `cloud_providers` list contains "Digital Ocean" and is sorted in alphabetical order.

I hope you enjoyed this blog post and learned something new. If you have any questions or suggestions, feel free to leave a comment below or contact me on LinkedIn or GitHub. I would love to hear from you!

1. Edit this textLinkedIn (**linkedin.com/in/vedant-adhe-4683b0192****) and**
    
2. **GitHub (**[**github.com/VedantAdhe**](http://github.com/VedantAdhe)**)**
    
3. **Connect** [**Vedantadhe19@gmail.com**](mailto:Vedantadhe19@gmail.com)
    

<s>!!!!!Thank you for reading !!!!!!</s>