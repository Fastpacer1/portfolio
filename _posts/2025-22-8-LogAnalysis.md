---
title: "SOC Analyst Simulation: Blue Team Threat Detection"
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

## Brute-Force Attack Target

Detected repeated login attempts against the /rest/user/login endpoint, indicating a brute-force attack vulnerability.

![1](https://fastpacer1.github.io/portfolio/assets/images/BlueTea/bruteforce.png)
> Brute-force attack

## SQL Injection Exploit

Identified /rest/products/search endpoint as vulnerable to SQL injection.

![1](https://fastpacer1.github.io/portfolio/assets/images/BlueTea/sqlinjection.png)

> The attacker used the q parameter to execute SQL injection attacks.

## Unauthorized File Retrieval Attempt

![1](https://fastpacer1.github.io/portfolio/assets/images/BlueTea/ftp.png) 

The attacker attempted to use ftp to retrieve files but failed.

# Phase 2

## Objective: Perform deeper log analysis to trace attacker movement, analyze response codes, and identify abnormal query strings.

## Website Scraping Activity

![1](https://fastpacer1.github.io/portfolio/assets/images/BlueTea/reviews.png) 

Detected attacker scraping user email addresses through the /reviews section of the website.

## Brute-Force Attack Result

![1](https://fastpacer1.github.io/portfolio/assets/images/BlueTea/timestamp.png) 

Brute-force attempt against /rest/user/login was successful.

## User Information Disclosure

![1](https://fastpacer1.github.io/portfolio/assets/images/BlueTea/email,password.png) 

The SQL injection vulnerability allowed the attacker to retrieve sensitive user information including emails and passwords.

## File Download Attempts

![1](https://fastpacer1.github.io/portfolio/assets/images/BlueTea/ftp.png)

From the vulnerable endpoint, the attacker attempted to download files such as /www-data.bak and /coupons_2013.md.bak.

## File Retrieval Method

![1](https://fastpacer1.github.io/portfolio/assets/images/BlueTea/anon.png)

Service: FTP 

Account Used: anonymous

## Shell Access Obtained

![1](https://fastpacer1.github.io/portfolio/assets/images/BlueTea/username.png)

Service: SSH

Username: wwww-data
