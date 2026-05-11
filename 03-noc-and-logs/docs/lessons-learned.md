# Lessons Learned - Zabbix Home NOC Lab

This document summarizes the main lessons learned during the creation of the Zabbix Home NOC Lab.

The project focused on infrastructure monitoring, UniFi API integration, switch port visibility, server monitoring and NOC dashboard design.

---

## 1. NOC and SOC Have Different Purposes

One important lesson was understanding the difference between NOC and SOC monitoring.

A NOC focuses on:

- Availability
- Performance
- Infrastructure health
- Network visibility
- Device status
- Operational alerts

A SOC focuses on:

- Security logs
- Suspicious activity
- Authentication events
- Threat detection
- Incident investigation
- Security anomalies

In this lab:

```text
Zabbix = NOC layer
Splunk = SOC layer
```

This separation made the architecture clearer and more realistic.

---

## 2. API Monitoring Can Be Better Than SNMP for Some Devices

The UniFi CloudKey did not respond to SNMP on UDP port 161.

After testing with `snmpwalk` and `nmap`, it was clear that SNMP was not available on the CloudKey itself.

However, the UniFi API worked successfully and returned useful data.

This showed that monitoring should be adapted to the device and available interfaces.

```text
CloudKey -> API monitoring
Access Points -> SNMP / API / ICMP monitoring
Switch -> API monitoring
```

The best monitoring method depends on what each device exposes.

---

## 3. SNMP and API Are Complementary

SNMP is useful for direct device-level monitoring, especially for network devices.

API monitoring is useful for controller-level visibility and structured data.

In this lab:

- SNMP worked for Access Points
- API worked for the UniFi Controller and switch data
- ICMP provided basic availability checks

This showed that a good monitoring design can combine multiple methods.

---

## 4. Total Traffic Is Not the Same as Current Traffic

The UniFi API provided total RX and TX counters.

At first, these values showed accumulated traffic.

To show current traffic rate, it was necessary to calculate the difference between readings.

In Zabbix, this was done using:

```text
Change per second
Custom multiplier = 8
Units = bps
```

This transformed byte counters into current bit-per-second traffic rates.

This was an important lesson in network monitoring.

```text
Total RX/TX = accumulated traffic
RX/TX Rate = current traffic usage
```

---

## 5. Dashboards Should Be Operationally Useful

A dashboard should not only look good. It should also help with operations.

The dashboard was designed to show:

- Switch port traffic
- PoE usage
- UniFi API status
- CPU usage
- Linux server health
- Active problems

This makes the dashboard useful for quick operational checks.

A good NOC dashboard should help answer questions such as:

```text
Are devices online?
Which port is using traffic?
Is PoE being used?
Is the monitoring server healthy?
Are there active problems?
Is the API working?
```

---

## 6. Naming Matters

The original environment had real device names and hostnames.

For public sharing, names were changed to generic labels.

Examples:

```text
WIN-ENDPOINT-01
AP Zone 1
AP Zone 2
AP Zone 3
Camera 01
Camera 02
```

This improved privacy and made the dashboard look more professional.

It also made the project easier to understand for someone viewing it on GitHub or LinkedIn.

---

## 7. Zabbix Agent Passive vs Active

During the lab, I reviewed the difference between passive and active Zabbix Agent monitoring.

### Passive Agent

```text
Zabbix Server -> Agent
```

The Zabbix Server connects to the monitored host.

### Active Agent

```text
Agent -> Zabbix Server
```

The monitored host connects to the Zabbix Server.

Active monitoring is useful when the endpoint is behind a firewall or when inbound connections to the endpoint are not preferred.

---

## 8. Problems View Adds Real Operational Value

The Problems widget helped make the dashboard more realistic.

It showed alerts such as:

```text
Zabbix agent unavailable
Installed packages changed
No data received
```

This is important because real monitoring is not just about metrics. It is also about detecting and responding to operational problems.

---

## 9. Privacy Is Important in Portfolio Projects

Before publishing screenshots or configuration files, sensitive information must be reviewed.

The lab exposed or handled information such as:

- Passwords
- API responses
- Hostnames
- MAC addresses
- Internal IP addresses
- Device names

For a public GitHub portfolio, these should be removed, masked or replaced with generic values.

Public screenshots should avoid showing:

```text
passwords
tokens
real usernames
sensitive MAC addresses
personal device names
public IP addresses
```

---

## 10. Home Labs Can Demonstrate Real Skills

This project showed that a home lab can demonstrate practical skills used in real IT operations.

Skills demonstrated include:

- Zabbix installation
- Monitoring design
- UniFi API integration
- Switch port monitoring
- PoE monitoring
- Linux server monitoring
- Windows endpoint monitoring
- Dashboard creation
- Alert visualization
- Troubleshooting
- Documentation
- Privacy-conscious publishing

Even though this is a home lab, the concepts are similar to real NOC environments.

---

## Key Technical Lessons

### UniFi API

The UniFi API can provide rich monitoring data, including device status, switch ports, PoE usage and connected devices.

### SNMP

SNMP is useful, but not every device exposes it in the same way.

### ICMP

ICMP is simple but valuable for availability checks.

### Zabbix Preprocessing

Zabbix preprocessing is powerful for transforming raw data into useful metrics.

### Dashboards

Good dashboards should combine:

- Status
- Performance
- Traffic
- Problems
- Availability
- Context

---

## Future Learning Goals

After completing this stage of the lab, future improvements include:

- Creating more detailed switch port dashboards
- Adding traffic graphs per port
- Adding AP client count widgets
- Monitoring wireless signal and noise
- Improving Windows endpoint monitoring
- Adding alert notifications
- Monitoring backups
- Adding firewall monitoring
- Adding UPS monitoring
- Creating a full SOC/NOC architecture diagram
- Documenting the full installation process step by step

---

## Summary

The Zabbix Home NOC Lab helped me understand how to build practical infrastructure monitoring using real network devices and a real monitoring platform.

The most important lesson was that monitoring should be adapted to each data source.

Some devices are best monitored by API, others by SNMP, others by agent or ICMP.

The final dashboard provides a useful NOC-style view of the home lab environment and complements the Splunk SOC lab created earlier.
