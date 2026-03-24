# Multi-Stage Attack Simulation

## Objective

Simulate and detect a real-world attack lifecycle.

## Attack Steps

### 1. Reconnaissance

* Tool: Nmap
* Command:
  nmap -sS <target-ip>

### 2. Brute Force Attack

* Tool: Hydra
* Command:
  hydra -l root -P rockyou.txt ssh://<target-ip>

### 3. Post-Compromise Activity

* Created and modified file in /tmp directory

## Detection

* SSH brute force detected using custom Wazuh rule (ID: 100005)
* Multiple failed login attempts correlated
* File integrity monitoring detected file changes

## Response

* Attacker IP automatically blocked using firewall-drop active response

## Investigation

* Logs analyzed using Wazuh dashboard
* Timeline reconstructed using field-based queries

## Conclusion

The system successfully detected and mitigated a multi-stage attack using SIEM-based monitoring and automated response.
