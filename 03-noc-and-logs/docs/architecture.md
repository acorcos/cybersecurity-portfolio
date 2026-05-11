# Architecture - Zabbix Home NOC Lab

This document describes the architecture used in the Zabbix Home NOC Lab.

The goal of this architecture is to separate infrastructure monitoring from security log monitoring, creating a basic home SOC/NOC lab environment.

---

## High-Level Architecture

```text
Home Network Devices
        |
        | UniFi API / ICMP / SNMP
        v
Zabbix Server
        |
        v
NOC Dashboard
```

The Zabbix environment is used to monitor infrastructure health, availability, switch ports, PoE usage, server metrics and operational problems.

In parallel, Splunk is used as the SIEM/log analysis layer.

```text
UniFi CloudKey / Network Devices
        |
        | Syslog
        v
Splunk Enterprise
        |
        v
SOC Dashboard
```

Together, Zabbix and Splunk provide a basic home SOC/NOC structure.

---

## Components

### Zabbix Server

The Zabbix Server runs on a Linux virtual machine and is responsible for:

- Collecting monitoring data
- Processing item values
- Running discovery rules
- Storing historical metrics
- Displaying dashboards
- Showing active problems and alerts

The same Linux VM is also used as part of the home cyber operations lab environment.

---

### UniFi CloudKey / Network Controller

The UniFi CloudKey is monitored through the UniFi Network API.

The API provides information such as:

- Device status
- Switch port data
- Access point information
- Connected devices
- Port traffic
- PoE usage
- Device uptime
- Wireless metadata

The CloudKey itself did not expose SNMP on UDP port 161, so API-based monitoring was used instead.

---

### UniFi Switch

The UniFi switch is monitored through the UniFi API using the Zabbix UniFi template.

The dashboard displays switch port information such as:

- Current port traffic
- Port speed
- PoE power usage
- Connected device role
- Free ports
- Uplink/device mapping

Example dashboard cards:

| Port | Role |
|---|---|
| Port 1 | CloudKey |
| Port 2 | Camera 01 |
| Port 3 | AP Zone 1 |
| Port 4 | AP Zone 2 |
| Port 5 | Free |
| Port 6 | Camera 02 |
| Port 7 | Free |
| Port 8 | AP Zone 3 |

---

### Access Points

Access Points can be monitored using a combination of:

- UniFi API
- SNMP
- ICMP checks

SNMP was tested successfully on UniFi Access Points. This allows APs to be monitored directly when supported.

---

### Linux Server

The Linux server is monitored using Zabbix Agent.

Collected metrics include:

- CPU usage
- Memory usage
- Disk usage
- Cache usage
- Operating system version
- Installed package changes
- Zabbix server health

---

### Windows Endpoint

A Windows endpoint was added to the lab to practice endpoint monitoring.

The Windows host can be monitored using:

- Zabbix Agent
- Zabbix Agent Active

This allows the dashboard to show endpoint availability and related problems.

---

## Monitoring Flow

### UniFi API Monitoring

```text
Zabbix Server
        |
        | HTTPS API request
        v
UniFi CloudKey / Controller
        |
        | JSON response
        v
Zabbix Items and Dashboards
```

The UniFi API is used to collect controller-level and device-level information.

---

### Server Monitoring

```text
Linux Server
        |
        | Zabbix Agent
        v
Zabbix Server
        |
        v
NOC Dashboard
```

The Zabbix Agent collects operating system metrics and sends them to the Zabbix Server.

---

### Endpoint Monitoring

```text
Windows Endpoint
        |
        | Zabbix Agent / Active Agent
        v
Zabbix Server
```

The endpoint can be monitored using either passive or active checks.

---

### SOC/SIEM Flow

```text
UniFi Devices / Windows Logs
        |
        | Syslog / Forwarder
        v
Splunk Enterprise
        |
        v
SOC Dashboards
```

Splunk is used for security event monitoring, log analysis and SIEM-style visibility.

---

## Design Approach

The lab follows a practical separation of responsibilities:

| Tool | Purpose |
|---|---|
| Zabbix | NOC, availability, infrastructure metrics |
| Splunk | SOC, logs, security events |
| UniFi API | Network device metadata and switch statistics |
| SNMP | Device-level monitoring where supported |
| ICMP | Basic availability checks |
| Zabbix Agent | Server and endpoint health |

---

## Why API Was Used for the CloudKey

During the lab, SNMP was tested against the UniFi CloudKey.

The result showed that UDP port 161 was closed on the CloudKey, meaning the device was not exposing SNMP directly.

Because of this, the UniFi API was used instead.

This approach allowed Zabbix to collect useful information such as:

- CloudKey status
- UniFi device list
- Switch port statistics
- PoE power usage
- Access point information
- Connected clients
- Device uptime
- Port traffic counters

This made API-based monitoring the most appropriate method for the CloudKey.

---

## Switch Port Traffic Calculation

The UniFi API provides total RX and TX counters for switch ports.

To display current traffic rate, Zabbix preprocessing was used.

The logic is:

```text
Total RX/TX counter
        |
        | Change per second
        v
Bytes per second
        |
        | Custom multiplier = 8
        v
Bits per second
```

This allows the dashboard to show current traffic usage in:

- bps
- Kbps
- Mbps
- Gbps

This is more useful for operational monitoring than only displaying accumulated traffic totals.

---

## Privacy Considerations

For public sharing, sensitive values were removed or masked.

The public version does not include:

- Real passwords
- API tokens
- Sensitive MAC addresses
- Public IP addresses
- Personal device names
- Internal security credentials

Generic names are used where appropriate, such as:

```text
WIN-ENDPOINT-01
AP Zone 1
AP Zone 2
AP Zone 3
Camera 01
Camera 02
```

---

## Summary

This architecture provides a practical foundation for a home SOC/NOC lab.

Zabbix provides the infrastructure and availability monitoring layer, while Splunk provides the security log and SIEM layer.

The combination of UniFi API monitoring, switch port visibility, server monitoring and active problem tracking creates a realistic operational monitoring environment for learning and portfolio purposes.