---
title: "Implementing and Testing Access Control Lists (ACLs) in Linux"
classes: wide
date: 2025-02-11
categories: 
  - Project
last_modified_at: 2025-02-11
---
# Implementing and Testing Access Control Lists (ACLs) in Linux

## Applying Access Control Lists

![1](https://fastpacer1.github.io/portfolio/assets/images/AccessControlListProject/1.png)

> Figure 1: Applying Access Control Lists permission to the testfile for bob

This figure shows the command sudo setfacl -m u:bob:rw testfile to Use Access Control Lists to grant specific permissions read/write access to bob.

![2](https://fastpacer1.github.io/portfolio/assets/images/AccessControlListProject/2.png)

> Figure 1.2: Applying Access Control Lists permission to the testfile for alice

This figure shows the command sudo setfacl -m u:alice:r testfile to use access control lists to grant specific permissions read-only access to alice

![3](https://fastpacer1.github.io/portfolio/assets/images/AccessControlListProject/3.png)

#Verifying Configuration

![4](https://fastpacer1.github.io/portfolio/assets/images/AccessControlListProject/4.png)

> Figure 2: Viewing the Access Control Lists for the testfile

This figure shows the command getfacl testfile being used to display the access control list configuration for the file.

#Testing Access Control

![5](https://fastpacer1.github.io/portfolio/assets/images/AccessControlListProject/5.png)

> Figure 3: Viewing the testfile after configuring the access control for it

This figure shows Bob using the command nano testfile.txt to open the file.

![6](https://fastpacer1.github.io/portfolio/assets/images/AccessControlListProject/6.png)

> Figure 3.1: Editing the file as a user with permissions

This figure shows that Bob can write to the testfile.txt file because he has the necessary permissions..

![7](https://fastpacer1.github.io/portfolio/assets/images/AccessControlListProject/7.png)

> Figure 3.2: Reading the file with bob who has permissions to do that

This figure shows Bob successfully reading the file using the cat command.

![8](https://fastpacer1.github.io/portfolio/assets/images/AccessControlListProject/8.png)
![9](https://fastpacer1.github.io/portfolio/assets/images/AccessControlListProject/9.png)

> Figure 3.3: Alice being unable to write into the testfile

This figure shows that Alice cannot write to the file because she only has read permissions.

![10](https://fastpacer1.github.io/portfolio/assets/images/AccessControlListProject/10.png)

> Figure 3.4: Alice being able to view the file

This figure shows Alice using the cat command to read the file, as she has the necessary read permissions.

![11](https://fastpacer1.github.io/portfolio/assets/images/AccessControlListProject/11.png)

> Figure 3.5: Kent attempting to view a file without the proper permissions

This figure shows that Kent cannot read the file because he is classified as "other," and the file's permissions do not allow access to others.
