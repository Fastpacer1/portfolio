---
title: "Hands-On SOC Project: Endpoint Exploitation & Incident Response"
classes: wide
date: 2025-08-22
categories: 
  - Project
last_modified_at: 2025-08-22
---

## Objective: Conduct log analysis to detect attacker activity, identify exploited endpoints, and assess vulnerabilities.

## Attacker Tools Identified

Analyzed log files to determine the tools used by the attacker in order of occurrence

![1](https://fastpacer1.github.io/portfolio/assets/images/BlueTea/nmap.png)
> Tool Used: Nmap

![2](https://fastpacer1.github.io/portfolio/assets/images/BlueTea/hydra.png)
> Tool Used: Hydra

![3](https://fastpacer1.github.io/portfolio/assets/images/BlueTea/sqlmap.png)
> Tool Used: Sqlmap

![4](https://fastpacer1.github.io/portfolio/assets/images/BlueTea/curl.png)
> Tool Used: Curl

![1](https://fastpacer1.github.io/portfolio/assets/images/BlueTea/feroxbuster.png)
> Tool Used: Feroxbuster

Reviewed access logs line by line to identify distinct strings and request patterns, mapping them to known attacker tools. This helped identify the attacker’s initial reconnaissance and exploitation phase.

## Brute-Force Attack Target

Detected repeated login attempts against the /rest/user/login endpoint, indicating a brute-force attack vulnerability.

![1](https://fastpacer1.github.io/portfolio/assets/images/BlueTea/bruteforce.png)
> Brute-force attack

Tracked failed login attempts across multiple IP addresses and identified the endpoint targeted for brute-force. This demonstrated how attackers tested authentication weaknesses.

## SQL Injection Exploit

Identified /rest/products/search endpoint as vulnerable to SQL injection.

![1](https://fastpacer1.github.io/portfolio/assets/images/BlueTea/sqlinjection.png)

> The attacker used the q parameter to execute SQL injection attacks.

Analyzed query strings in the logs and confirmed use of the q parameter for SQL injection. This revealed how attackers exfiltrated data from the backend database.

## Unauthorized File Retrieval Attempt

The attacker attempted to use ftp to retrieve files but failed.

![1](https://fastpacer1.github.io/portfolio/assets/images/BlueTea/ftp.png) 

Noticed repeated FTP requests attempting to download restricted files. Although these attempts failed, it highlighted the attacker’s persistence in testing multiple vectors.

# Phase 2 - Post-Exploitation & Escalation

## Objective: Perform deeper log analysis to trace attacker movement, analyze response codes, and identify abnormal query strings.

## Website Scraping Activity

Detected attacker scraping user email addresses through the /reviews section of the website.

![1](https://fastpacer1.github.io/portfolio/assets/images/BlueTea/reviews.png) 

Examined repetitive GET requests with abnormal frequency and identified scraping activity aimed at harvesting sensitive user data.

## Brute-Force Attack Result

Brute-force attempt against /rest/user/login was successful.

![1](https://fastpacer1.github.io/portfolio/assets/images/BlueTea/timestamp.png) 

Verified the single successful login attempt after multiple failures and documented the timestamp for incident timeline reconstruction.

## User Information Disclosure

The SQL injection vulnerability allowed the attacker to retrieve sensitive user information including emails and passwords.

![1](https://fastpacer1.github.io/portfolio/assets/images/BlueTea/email,password.png) 

Tracked SQL injection payloads and confirmed that sensitive fields (emails, hashed passwords) were disclosed.

## File Download Attempts

From the vulnerable endpoint, the attacker attempted to download files such as /www-data.bak and /coupons_2013.md.bak.

![1](https://fastpacer1.github.io/portfolio/assets/images/BlueTea/ftp.png)

Validated attacker requests targeting backup and configuration files, which are often leveraged for privilege escalation.

## File Retrieval Method

Monitored service-level access logs and confirmed the attacker’s attempt to use anonymous FTP for file retrieval.

![1](https://fastpacer1.github.io/portfolio/assets/images/BlueTea/anon.png)

Service: FTP 

Account Used: anonymous

## Shell Access Obtained

Identified the log entry confirming shell access via SSH under the compromised www-data account, marking the final stage of attacker compromise.

![1](https://fastpacer1.github.io/portfolio/assets/images/BlueTea/username.png)

Service: SSH

Username: wwww-data

## Analysis Summary

Through this investigation, I reconstructed the attacker’s full kill chain: reconnaissance → brute-force → SQL injection → data exfiltration → file retrieval attempts → remote shell access.
This exercise strengthened my ability to:

* Analyze and interpret raw log files.

* Correlate attacker actions across multiple services.

* Identify exploited endpoints and sensitive data exposure.

* Document findings in a structured, SOC-ready format.

Outcome: Practical experience in threat detection, log analysis, and incident response, simulating real-world SOC analyst duties.
