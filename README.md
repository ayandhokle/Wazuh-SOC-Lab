# Wazuh SOC Lab

## Overview

This project demonstrates a home SOC (Security Operations Center) lab built using Wazuh SIEM.

## Lab Architecture

* Ubuntu: Wazuh Manager
* Kali Linux: Attacker + Agent
* Network: NAT

## Attack Scenarios

* Nmap reconnaissance
* SSH brute force attack
* File integrity monitoring (FIM)

## Detection Engineering

* Custom Wazuh rule for SSH brute force detection
* Correlation using same source IP

## Response

* Automated IP blocking using active response (firewall-drop)

## Monitoring & Analysis

* Log analysis using Wazuh dashboard
* Field-based queries for investigation

## Skills Demonstrated

* SIEM configuration
* Threat detection
* Incident response
* Log analysis
* Detection rule creation

## Key Achievement

Built a complete SOC workflow:
Detection → Correlation → Automated Response → Investigation
