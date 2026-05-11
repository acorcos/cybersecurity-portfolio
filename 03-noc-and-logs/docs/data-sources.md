\# Data Sources - Zabbix Home NOC Lab



This document describes the data sources used in the Zabbix Home NOC Lab.



The project collects data from UniFi devices, Linux servers, Windows endpoints and network availability checks.



\---



\## 1. UniFi API



The UniFi Network API is the main data source for network device monitoring.



The Zabbix template connects to the UniFi CloudKey / Network Controller and retrieves JSON data from the controller.



\### Purpose



The UniFi API is used to monitor:



\- CloudKey / Controller status

\- UniFi devices

\- Switch ports

\- Access points

\- Connected clients

\- Port statistics

\- PoE usage

\- Device uptime

\- Wireless metadata



\---



\## 2. Example API Endpoints



The lab used API endpoints similar to:



```text

/api/auth/login

/proxy/network/api/s/default/stat/device-basic

/proxy/network/api/s/default/stat/device

```



The authentication endpoint is used to log in to the UniFi controller.



The device endpoints return information about UniFi switches, access points and connected devices.



\---



\## 3. Example Data Returned



The UniFi API can return data such as:



```text

device name

device type

MAC address

IP address

state

model

firmware version

port table

PoE power

RX bytes

TX bytes

connected clients

wireless channel

wireless noise

uptime

```



For public sharing, sensitive values such as MAC addresses, tokens, usernames and internal identifiers should be removed or masked.



\---



\## 4. Why API Instead of SNMP for CloudKey?



SNMP was tested against the UniFi CloudKey, but UDP port 161 was closed.



Because the CloudKey did not expose SNMP directly, the UniFi API was used as the main monitoring method.



This provided better visibility into controller-level and device-level data.



\---



\## 5. UniFi Switch Data



The UniFi switch is monitored through the UniFi API.



The Zabbix UniFi switch template discovers switch ports and creates items for each port.



\### Switch Port Metrics



Examples of collected metrics:



```text

Port enabled

Port status

Port speed

Port name

Port mode

Port media

PoE capable

PoE good

PoE mode

PoE power

Total RX

Total TX

RX packets

TX packets

RX errors

TX errors

RX dropped

TX dropped

RX broadcast

TX broadcast

RX multicast

TX multicast

```



\---



\## 6. Current Traffic Rate



The original UniFi API provides total RX/TX counters.



To display current traffic usage, new Zabbix items were created using:



```text

Change per second

Custom multiplier = 8

Units = bps

```



This converts byte counters into current bit-per-second traffic rates.



Example logic:



```text

Total RX counter

&#x20;       |

&#x20;       | Change per second

&#x20;       v

Bytes per second

&#x20;       |

&#x20;       | Custom multiplier = 8

&#x20;       v

Bits per second

```



This allows dashboard cards to show values such as:



```text

253 Kbps

1.5 Mbps

2.5 Mbps

```



\---



\## 7. UniFi Access Points



UniFi Access Points can be monitored through:



\- UniFi API

\- SNMP

\- ICMP



SNMP was tested successfully on Access Points.



\### Example SNMP Test



```bash

snmpwalk -v2c -c '<community>' <ap-ip> 1.3.6.1.2.1.1

```



The Access Point returned information such as:



```text

device model

system name

uptime

system description

```



\---



\## 8. Access Point Metrics



Depending on the template and monitoring method, AP monitoring may include:



```text

AP state

AP adopted status

AP uptime

AP IP address

AP MAC address

AP model

AP firmware version

CPU usage

Memory usage

Wireless channel

Wireless radio

TX power

TX retries

Connected clients

Wireless signal

Wireless noise

```



\---



\## 9. Zabbix Agent - Linux Server



The Linux server running Zabbix is monitored using Zabbix Agent.



\### Collected Metrics



```text

CPU usage

Memory usage

Disk usage

Cache usage

Operating system version

Installed packages

Agent availability

Zabbix server health

```



These metrics are used in the dashboard to show server health and resource usage.



\---



\## 10. Zabbix Agent - Windows Endpoint



A Windows endpoint was added to the lab to practice endpoint monitoring.



Two monitoring modes are possible:



\### Passive Agent



```text

Zabbix Server -> Windows Agent

```



The Zabbix Server initiates the connection to the Windows endpoint.



\### Active Agent



```text

Windows Agent -> Zabbix Server

```



The Windows endpoint initiates the connection and sends data to the Zabbix Server.



The active agent approach is useful when the endpoint is behind firewall or NAT restrictions.



\---



\## 11. ICMP Availability Checks



ICMP checks can be used to confirm basic reachability of network devices.



Examples:



```text

CloudKey availability

Switch availability

Access Point availability

Camera availability

Endpoint availability

```



ICMP monitoring is useful as a simple availability layer even when API or SNMP monitoring is also configured.



\---



\## 12. Problems and Alerts



Zabbix also provides operational problem data.



Examples of problems shown in the dashboard:



```text

Zabbix agent unavailable

No data received for a defined period

Installed packages changed

Device unreachable

Monitoring data gaps

```



The Problems widget helps simulate a real NOC workflow.



\---



\## Data Source Summary



| Data Source | Method | Purpose |

|---|---|---|

| UniFi CloudKey | API | Controller and network data |

| UniFi Switch | API | Port traffic, PoE and switch status |

| UniFi APs | API / SNMP / ICMP | Wireless device monitoring |

| Linux Server | Zabbix Agent | Server health |

| Windows Endpoint | Zabbix Agent / Active Agent | Endpoint health |

| Network Devices | ICMP | Availability checks |

| Zabbix Problems | Internal Zabbix data | Alert and incident visibility |



\---



\## Privacy Notes



Before publishing data or screenshots, the following information should be reviewed and masked:



\- Passwords

\- API tokens

\- SNMP communities

\- Real MAC addresses

\- Sensitive hostnames

\- Personal device names

\- Public IP addresses

\- Internal usernames



For this public lab, generic names are preferred, such as:



```text

WIN-ENDPOINT-01

AP Zone 1

AP Zone 2

AP Zone 3

Camera 01

Camera 02

```



\---



\## Summary



The lab uses multiple data sources to create a realistic NOC dashboard.



The UniFi API provides rich network visibility, Zabbix Agent provides server and endpoint metrics, SNMP is used where supported, and ICMP provides simple availability checks.



Together, these sources create a practical monitoring environment for infrastructure visibility and NOC-style operations.

