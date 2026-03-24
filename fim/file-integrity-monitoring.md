# File Integrity Monitoring (FIM)

## Objective

To detect unauthorized file changes and simulate post-compromise activity using Wazuh File Integrity Monitoring.

---

## Configuration

FIM was configured in the Wazuh manager configuration file:

/var/ossec/etc/ossec.conf

### Key Settings

* Enabled syscheck: <disabled>no</disabled>

* Reduced scan frequency for real-time detection: <frequency>60</frequency>

* Enabled scan on start:
  <scan_on_start>yes</scan_on_start>

---

## Monitored Directory

Added a custom directory for monitoring:

<directories check_all="yes">/tmp</directories>

This allowed detection of suspicious file activity in a commonly abused directory.

---

## Test Scenario

Simulated attacker behavior by creating and modifying a file:

Commands used:

touch /tmp/hacked.txt
echo "malicious content" >> /tmp/hacked.txt
rm /tmp/hacked.txt

---

## Detection

Wazuh successfully generated alerts for:

* File creation
* File modification
* File deletion

---

## Log Analysis

Logs were analyzed in the Wazuh dashboard using structured queries:

Examples:

* data.path:/tmp/hacked.txt
* rule.groups:syscheck

---

## Challenges Faced

* Incorrect XML syntax initially prevented monitoring
* Scan frequency was too high (12 hours), delaying detection
* Required understanding of field-based search queries

---

## Outcome

Successfully implemented File Integrity Monitoring with:

* Real-time detection
* Full file lifecycle visibility
* Accurate log analysis using SIEM queries

---

## Key Learning

Understanding how to configure and tune FIM is critical for detecting:

* Unauthorized file access
* Persistence mechanisms
* Post-exploitation activity
