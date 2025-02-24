---
title: "Using an incident response playbook to handle a phishing attack."
classes: wide
date: 2025-02-11
categories: 
  - Project
last_modified_at: 2025-02-23
---

## Using an incident response playbook to handle a phishing attack

**Scenerio:**

You are a level-one security operations center (SOC) analyst at a financial services company. Previously, you received a phishing alert about a suspicious file being downloaded on an employee's computer. 
After investigating the email attachment file's hash, the attachment has already been verified malicious. Now that you have this information, you must follow your organization's process to complete your investigation
and resolve the alert.

This incident response begins with recieving an alert ticket which indicates a potential phising attempt. 

> I proceeded to analyze the ticket, setting the Ticket status to investigating, which is Step 2 of the phishing incident response playbook, following the receipt of the phishing alert outlined in Step 1.

![image1](https://fastpacer1.github.io/portfolio/assets/images/IncidentResponce/image1.png)

>> *Figure 1: Alert Ticket*

![image3](https://fastpacer1.github.io/portfolio/assets/images/IncidentResponce/image3.png)

>> *Figure 2: Phising incident response playbook Step 1*

Following the analysis of the Alert ticket, I reviewed the phising incident response playbook to determing the next steps.

![image2](https://fastpacer1.github.io/portfolio/assets/images/IncidentResponce/image2.png)
>> *Figure 3: Phising incident response playbook*

After reviewing the phising incident response playbook i can determing that the alert contained an attachment, which can be seen to be an executable file, a hash was also included in the alert, and labled as malicious.
To determine whether the attachment was malicious i evaluated the header and body of the email which contained multiple spelling errors, this is an initial indicator of a phising attempt, but further investigation would be needed.

*I proceeded to investigate the file hash using VirusTotal.*

![image4](https://fastpacer1.github.io/portfolio/assets/images/IncidentResponce/image4.png)
>> *Figure 4: Virustotal investigation*

The file has been identified by 60 vendors as malicious. Using the playbook i determined that this needed to be escalated to notify a level-two SOC analyst, while providing context as to why i chose to escalate the ticket.

![image5](https://fastpacer1.github.io/portfolio/assets/images/IncidentResponce/image5.png)

>> *Figure 5: Ticket escalation*

**Reflection**

In this activity, I investigated a phishing attempt using an incident response playbook. This project provided hands-on experience in applying a playbook to guide the response process.
