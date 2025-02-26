---
title: "Algorithm for file updates in Python"
classes: wide
date: 2025-02-26
categories: 
  - Project
last_modified_at: 2025-02-26
---

## Updating a file through a Python algorithm

**Scenerio**

You are a security professional working at a health care company. As part of your job, you're required to regularly update a file that identifies the employees who can access restricted content.
The contents of the file are based on who is working with personal patient records. Employees are restricted access based on their IP address.
There is an allow list for IP addresses permitted to sign into the restricted subnetwork. There's also a remove list that identifies which employees you must remove from this allow list.

Your task is to create an algorithm that uses Python code to check whether the allow list contains any IP addresses identified on the remove list. If so, you should remove those IP addresses from the file containing the allow list.


```
# Open the file that contains the allow list

import_file = "allow_list.txt"
```

remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]
```
#Read the file contents
with open(import_file, "r") as file:
  ip_addresses = file.read()
```

```
# Convert the string into a list
ipaddresses = ip_addresses.split()
```

```
# Iterate through the remove list
for i in ip_addresses:

# Remove IP addresses that are on the remove list
  if i in remove_list:
    ip_addresses.remove(i)
```
```
ip_addresses = " ".join(ip_addresses)
```

```
# Update the file with the revised list of IP addresses 
with open(import_file, "w") as file:
  file.write(ip_addresses)
```

**Project Description**

This project involves automating the management proccess of an allowed list for restricted network access in a healthcare setting. The script enabled only authorized employees to gain access to sensitive patient records
by removing the IP addresses placed in the remove list.

**Summary**

The python scripts reads an allowed list of IP addresses from "allow_list", checks for any matches againts the defined remove list, and removes all unauthorized IP addresses. 
The updated list is then written back to the original file. The script follows the structure:

1. Read the file and convert the contents into a list
2. Filters out any IP addresses found in the remove list
3. Rewrites the updated allowed list back to the original file.
