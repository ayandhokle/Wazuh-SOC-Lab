# Lab Setup

## Environment Overview

This lab simulates a basic SOC environment using Wazuh SIEM.

### Systems Used

* **Ubuntu Server**

  * Role: Wazuh Manager
  * Resources: 6GB RAM, 2 CPUs

* **Kali Linux**

  * Role: Attacker + Wazuh Agent
  * Resources: 4GB RAM, 2 CPUs

### Network Configuration

* Both machines are connected using a NAT network
* Direct communication enabled between attacker and target

---

## Wazuh Installation

### On Ubuntu (Manager)

Installed Wazuh manager and dashboard:

* Wazuh Manager
* Wazuh API
* Wazuh Dashboard

Services were verified and started successfully.

---

### On Kali Linux (Agent)

Installed Wazuh agent and connected to manager:

* Configured manager IP in agent configuration
* Registered agent with Wazuh manager
* Verified agent status in dashboard (Active)

---

## Firewall Configuration

Configured firewall using UFW:

* Allowed required Wazuh ports:

  * 1514 (agent communication)
  * 1515 (agent enrollment)

* Enabled logging:

  * Used for detecting reconnaissance activities (e.g., Nmap scans)

---

## Attack Simulation Tools

The following tools were used for attack simulation:

* **Nmap**

  * Used for network reconnaissance

* **Hydra**

  * Used for SSH brute force attack

---

## Logging & Monitoring

* Logs collected from:

  * SSH authentication logs
  * Firewall (UFW) logs
  * File Integrity Monitoring (FIM)

* Analysis performed using Wazuh dashboard (Discover section)

---

## Outcome

Successfully built a functional SOC lab environment capable of:

* Detecting attacks
* Correlating events
* Triggering automated responses
* Monitoring file integrity changes
