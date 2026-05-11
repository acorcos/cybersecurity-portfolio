\# Risk Assessment Summary - Botium Toys



\## Overview



This document summarizes the risk assessment for Botium Toys, a fictional company used in the Google Cybersecurity Certificate portfolio activity.



The purpose of this assessment is to identify current IT-managed assets, review existing risks, and highlight the main security gaps that may affect confidentiality, integrity, availability, compliance, and business continuity.



\## Current Assets Managed by the IT Department



The IT department manages several important assets that support both the physical store and the online business operations.



\### Main asset groups



\- On-premises equipment used for in-office business operations

\- Employee equipment, including desktops, laptops, smartphones, remote workstations, headsets, cables, keyboards, mice, docking stations, and surveillance cameras

\- Storefront products available for retail sale both on site and online

\- Warehouse inventory stored in the company’s adjoining warehouse

\- Systems, software, and services for accounting, telecommunications, databases, security, ecommerce, and inventory management

\- Internet access

\- Internal network

\- Data retention and storage systems

\- Legacy systems that require human monitoring and maintenance



\## Risk Description



Botium Toys currently has inadequate asset management and does not have all necessary security controls in place.



The company may also not be fully compliant with relevant U.S. and international regulations and standards, especially because it accepts online payments and conducts business with customers in the European Union.



This creates risks related to:



\- Unauthorized access to sensitive data

\- Exposure of customer PII/SPII

\- Exposure of cardholder data

\- Lack of compliance with PCI DSS and GDPR best practices

\- Weak business continuity and recovery capabilities

\- Limited ability to detect suspicious activity

\- Incomplete asset classification and inventory



\## Risk Score



The overall risk score is:



\*\*8 out of 10\*\*



This is considered a high risk score.



The high score is mainly due to the lack of key controls and gaps in compliance best practices.



\## Key Risk Findings



\### 1. Excessive access to sensitive data



All employees currently have access to internally stored data. This means they may be able to access customer PII/SPII and cardholder data, even if they do not need that access to perform their jobs.



This creates a confidentiality risk and shows that least privilege has not been properly implemented.



\### 2. Lack of encryption



Encryption is not currently used to protect customers’ credit card information that is accepted, processed, transmitted, and stored locally in the company’s internal database.



This increases the risk of exposing sensitive payment data if the database or internal systems are compromised.



\### 3. Least privilege is not implemented



The principle of least privilege has not been implemented.



Users may have more access than necessary, which increases the potential impact of compromised accounts, human error, or malicious insider activity.



\### 4. Separation of duties is not implemented



Separation of duties has not been implemented.



This creates a risk because one person or group may have too many permissions, increasing the chance of fraud, misuse, or unauthorized changes.



\### 5. Firewall is in place



The IT department has a firewall that blocks traffic based on an appropriately defined set of security rules.



This is a positive control that helps filter unwanted or malicious traffic from entering the network.



\### 6. Antivirus is installed and monitored



Antivirus software is installed and monitored regularly by the IT department.



This helps detect and quarantine known threats.



\### 7. No intrusion detection system



Botium Toys does not currently have an intrusion detection system, also known as IDS.



Without an IDS, the company has limited ability to quickly detect suspicious or anomalous network activity.



\### 8. No disaster recovery plan



There is currently no disaster recovery plan in place.



This creates a business continuity risk because the company may not be able to recover quickly after a major incident.



\### 9. No backups of critical data



The company does not have backups of critical data.



This is a serious risk because data loss caused by hardware failure, human error, ransomware, or another incident could significantly disrupt business operations.



\### 10. GDPR notification plan exists



Botium Toys has established a plan to notify E.U. customers within 72 hours if there is a security breach involving their data.



This supports GDPR compliance, but other privacy and access control gaps still need to be addressed.



\### 11. Privacy policies and procedures exist



Privacy policies, procedures, and processes have been developed and are enforced among IT department members and other employees to properly document and maintain data.



This is a positive compliance-related practice.



\### 12. Password policy is weak



A password policy exists, but its requirements are minimal and are not aligned with current minimum password complexity recommendations.



This increases the risk of account compromise through brute force, dictionary attacks, or credential guessing.



\### 13. No centralized password management system



There is no centralized password management system that enforces minimum password requirements.



This creates both security and productivity issues, especially when employees or vendors need password recovery or resets.



\### 14. Legacy systems lack a clear maintenance schedule



Legacy systems are monitored and maintained, but there is no regular schedule for these tasks and intervention methods are unclear.



This increases the risk that vulnerabilities in outdated systems may not be identified or remediated in time.



\### 15. Physical security controls are in place



The physical location has sufficient locks, up-to-date CCTV surveillance, and functioning fire detection and prevention systems.



These controls help protect the offices, storefront, warehouse, products, and physical IT assets.



\## Impact Summary



The potential impact from the loss of an asset is rated as medium because the IT department does not have a complete understanding of which assets are at risk.



However, the risk of asset loss or regulatory fines is high because Botium Toys does not have all necessary controls in place and is not fully following compliance best practices for protecting private and sensitive data.



\## Main Security Gaps



The most important gaps identified are:



\- Lack of least privilege

\- Lack of separation of duties

\- Weak password policy

\- No centralized password management system

\- No encryption for cardholder data

\- No IDS

\- No disaster recovery plan

\- No backups of critical data

\- Incomplete asset identification and classification

\- Excessive employee access to internal data, PII/SPII, and cardholder data

\- Unclear monitoring and maintenance process for legacy systems



\## Initial Risk Priorities



The most urgent areas to address are:



1\. Restrict access to sensitive data using least privilege

2\. Implement separation of duties

3\. Encrypt credit card and sensitive customer data

4\. Implement an IDS

5\. Create regular backups of critical data

6\. Develop and test a disaster recovery plan

7\. Strengthen password policies

8\. Deploy a centralized password management system

9\. Improve asset inventory and classification

10\. Establish a regular maintenance schedule for legacy systems



\## Conclusion



Botium Toys has some important controls already in place, such as firewall, antivirus, locks, CCTV, fire detection and prevention systems, and a GDPR breach notification plan.



However, the company still has several critical gaps in access control, data protection, detection, recovery, password management, and compliance practices.



Addressing these gaps will help reduce the current risk level, improve business continuity, better protect sensitive data, and strengthen the organization’s overall security posture.



\## Disclaimer



This project is based on a fictional scenario from the Google Cybersecurity Certificate and was created for educational and portfolio purposes.

