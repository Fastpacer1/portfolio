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
