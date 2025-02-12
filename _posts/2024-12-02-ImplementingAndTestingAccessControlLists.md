---
title: "Implementing and Testing Access Control Lists (ACLs) in Linux"
classes: wide
date: 2025-02-11
categories: 
  - Project
last_modified_at: 2025-02-11
---
## Applying Access Control Lists

![1](https://fastpacer1.github.io/portfolio/assets/images/AccessControlListProject/1.png)

> Figure 1: Applying Access Control Lists permission to the testfile for bob

Figure 1 demonstrates how to grant specific permissions to Bob using Access Control Lists (ACLs). The command sudo setfacl -m u:bob:rw testfile assigns read and write access to Bob for the file testfile.

![2](https://fastpacer1.github.io/portfolio/assets/images/AccessControlListProject/2.png)

> Figure 1.2: Applying Access Control Lists permission to the testfile for alice

Figure 1.2 shows how to grant Alice read-only access to testfile using ACLs. The command sudo setfacl -m u:alice:r testfile ensures that Alice can view the file but not modify it.

## Verifying Configuration

![3](https://fastpacer1.github.io/portfolio/assets/images/AccessControlListProject/3.png)

> Figure 2: Viewing the Access Control Lists for the testfile

Figure 2 illustrates how to verify the ACL settings applied to testfile. The command getfacl testfile is used to display the access control list configuration, confirming the assigned permissions.


## Testing Access Control
![4](https://fastpacer1.github.io/portfolio/assets/images/AccessControlListProject/4.png)


> Figure 3: Viewing the testfile after configuring the access control for it

Figure 3 shows Bob attempting to open testfile.txt using the nano command after ACL permissions have been configured.

![5](https://fastpacer1.github.io/portfolio/assets/images/AccessControlListProject/5.png)

> Figure 3.1: Editing the file as a user with permissions

Figure 3.1 confirms that Bob is able to edit testfile.txt since he has been granted read and write permissions.

![6](https://fastpacer1.github.io/portfolio/assets/images/AccessControlListProject/6.png)

> Figure 3.2: Reading the file with bob who has permissions to do that

Figure 3.2 demonstrates that Bob can successfully read the file using the cat command.

![7](https://fastpacer1.github.io/portfolio/assets/images/AccessControlListProject/7.png)
![8](https://fastpacer1.github.io/portfolio/assets/images/AccessControlListProject/8.png)

> Figure 3.3: Alice being unable to write into the testfile

Figure 3.3 illustrates Alice’s inability to write to testfile because she only has read permissions.

![9](https://fastpacer1.github.io/portfolio/assets/images/AccessControlListProject/9.png)

> Figure 3.4: Alice being able to view the file

Figure 3.4 shows Alice using the cat command to view the file, confirming that her read permissions are correctly applied.

![10](https://fastpacer1.github.io/portfolio/assets/images/AccessControlListProject/10.png)

> Figure 3.5: Kent attempting to view a file without the proper permissions

Figure 3.5 presents Kent attempting to read testfile without the necessary permissions. Since Kent is classified as "other" and no permissions have been granted to others, he is unable to access the file.

![11](https://fastpacer1.github.io/portfolio/assets/images/AccessControlListProject/11.png)

> Figure 3.6: Kent attempting to edit a file without the proper permissions

Figure 3.6 demonstrates Kent’s unsuccessful attempt to edit testfile. Because he is classified as "other" and does not have write access, he is unable to modify the file.


## Reflection

This exercise highlights the importance of Access Control Lists (ACLs) in managing file permissions beyond traditional Linux ownership and group-based access controls. By configuring ACLs, I was able to assign specific permissions to individual users, demonstrating how access management enhances security and control.

