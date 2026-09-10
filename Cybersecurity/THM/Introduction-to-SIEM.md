# Introduction to SIEM

**TryHackMe room:** Introduction to SIEM
**Status:** Completed

## What is SIEM?

**SIEM (Security Information and Event Management)** is a security solution used by SOC analysts to collect, centralize and analyze logs from different sources.

It can help with:

* centralized log collection
* log normalization
* log correlation
* real-time alerting
* dashboards and reporting

## Log Sources

A **log source** is a device or system that generates logs.

### Host-Centric

Logs related to activity occurring on a host.

Examples:

* Windows / Linux systems
* Servers
* Workstations
* Authentication attempts
* File access
* Process execution

### Network-Centric

Logs related to network communication.

Examples:

* Firewalls
* IDS/IPS
* Routers
* SSH connections
* FTP activity
* Web traffic
* VPN activity

## Why Use a SIEM?

Without a SIEM, logs are distributed across many systems and can have different formats. This makes investigation more difficult and can result in limited context or important events being missed.

A SIEM brings these logs together and can correlate events from different sources.

## Log Ingestion

Logs can be sent to a SIEM using different methods:

* **Agent / Forwarder** – software installed on an endpoint that forwards logs.
* **Syslog** – commonly used for sending logs to a centralized destination.
* **Manual upload** – logs can be uploaded for analysis.
* **Port forwarding** – endpoints can send data to a specific listening port.

## Detection Rules & Alerts

SIEMs use **detection rules** to identify specific patterns or events and generate alerts.

Examples:

* multiple failed login attempts
* successful login after multiple failures
* suspicious process execution
* cleared Windows event logs

When an alert is generated, the analyst investigates it and determines whether it is:

* **False Positive** – the alert does not represent the activity the rule was intended to detect.
* **True Positive** – the alert represents genuine suspicious activity and requires further investigation.

## Key Takeaways

* SIEM centralizes logs from different sources.
* Logs can be **host-centric** or **network-centric**.
* Log correlation provides more context during investigations.
* Detection rules can generate alerts based on specific events.
* SOC analysts investigate alerts and determine whether they are true or false positives.
* Log ingestion can be performed in several ways, including agents, Syslog, manual uploads and port forwarding.
