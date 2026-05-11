# Controls and Compliance Checklist - Botium Toys

This document presents the controls and compliance checklist for Botium Toys, a fictional company used in the Google Cybersecurity Certificate portfolio activity.

The checklist is based on the company’s scope, goals, risk assessment report, and the control categories provided in the course materials.

The purpose is to identify which controls and compliance best practices are currently in place and which ones need to be implemented or improved.

---

## Controls Assessment Checklist

### Administrative / Managerial Controls

| Control | Currently in place? | Notes |
|---|---|---|
| Least Privilege | No | Least privilege has not been implemented. All employees may have access to internally stored data, including PII/SPII and cardholder data. |
| Disaster Recovery Plans | No | There is no disaster recovery plan currently in place. |
| Password Policies | No | A password policy exists, but it is weak and does not meet current minimum complexity requirements. |
| Separation of Duties | No | Separation of duties has not been implemented. This increases the risk of misuse, fraud, or excessive access. |

---

### Technical Controls

| Control | Currently in place? | Notes |
|---|---|---|
| Firewall | Yes | A firewall is in place and blocks traffic based on defined security rules. |
| Intrusion Detection System (IDS) | No | No IDS has been installed, limiting the ability to detect suspicious or anomalous activity. |
| Backups | No | Botium Toys does not currently have backups of critical data. |
| Antivirus Software | Yes | Antivirus software is installed and monitored regularly by the IT department. |
| Manual Monitoring, Maintenance, and Intervention for Legacy Systems | No | Legacy systems are monitored and maintained, but there is no regular schedule and intervention methods are unclear. |
| Encryption | No | Encryption is not currently used to protect credit card information that is accepted, processed, transmitted, and stored locally. |
| Password Management System | No | There is no centralized password management system enforcing password requirements. |

---

### Physical / Operational Controls

| Control | Currently in place? | Notes |
|---|---|---|
| Locks - Offices, Storefront, Warehouse | Yes | The physical location has sufficient locks. |
| Closed-Circuit Television - CCTV Surveillance | Yes | Up-to-date CCTV surveillance is in place. |
| Fire Detection / Prevention | Yes | Functioning fire detection and prevention systems are in place. |

---

## Compliance Checklist

### Payment Card Industry Data Security Standard - PCI DSS

| Best Practice | Currently followed? | Notes |
|---|---|---|
| Only authorized users have access to customers’ credit card information | No | All employees may be able to access internally stored data, including cardholder data. |
| Credit card information is stored, accepted, processed, and transmitted internally in a secure environment | No | Credit card data is accepted, processed, transmitted, and stored locally, but encryption is not used. |
| Implement data encryption procedures to better secure credit card transaction touchpoints and data | No | Encryption is not currently implemented for credit card information. |
| Adopt secure password management policies | No | Password policies are weak and there is no centralized password management system. |

---

### General Data Protection Regulation - GDPR

| Best Practice | Currently followed? | Notes |
|---|---|---|
| E.U. customers’ data is kept private and secured | No | Employees may be able to access customer PII/SPII, which creates a confidentiality risk. |
| There is a plan in place to notify E.U. customers within 72 hours if their data is compromised or there is a breach | Yes | A notification plan exists for E.U. customers in case of a data breach. |
| Ensure data is properly classified and inventoried | No | Asset and data classification are incomplete, and the IT department does not fully know which assets are at risk. |
| Enforce privacy policies, procedures, and processes to properly document and maintain data | Yes | Privacy policies, procedures, and processes have been developed and are enforced. |

---

### System and Organizations Controls - SOC Type 1 / SOC Type 2

| Best Practice | Currently followed? | Notes |
|---|---|---|
| User access policies are established | No | Access controls related to least privilege and separation of duties have not been implemented. |
| Sensitive data - PII/SPII - is confidential and private | No | Employees may be able to access customers’ PII/SPII. |
| Data integrity ensures the data is consistent, complete, accurate, and validated | Yes | The IT department has integrated controls to ensure data integrity. |
| Data is available to individuals authorized to access it | Yes | The IT department has ensured availability controls. |

---

## Summary of Findings

Botium Toys has some security controls in place, including firewall, antivirus software, locks, CCTV surveillance, fire detection and prevention systems, and a GDPR breach notification plan.

However, several important controls and compliance best practices are missing or insufficient.

The most critical gaps include:

- Lack of least privilege
- Lack of separation of duties
- Weak password policies
- No centralized password management system
- No encryption for credit card data
- No intrusion detection system
- No backups of critical data
- No disaster recovery plan
- Incomplete asset and data classification
- No clear regular monitoring and maintenance schedule for legacy systems

These gaps increase the organization’s risk exposure, especially regarding confidentiality, compliance, incident detection, and business continuity.

---

## Priority Improvements

The following improvements should be prioritized:

1. Implement least privilege access controls
2. Apply separation of duties
3. Strengthen password policies
4. Deploy a centralized password management system
5. Implement encryption for credit card and sensitive customer data
6. Install an intrusion detection system
7. Create regular backups of critical data
8. Develop and test a disaster recovery plan
9. Improve asset and data classification
10. Establish a regular monitoring and maintenance schedule for legacy systems

---

## Conclusion

The controls and compliance checklist shows that Botium Toys has some foundational protections in place, but the organization still has significant gaps in access control, data protection, compliance, detection, and recovery.

Implementing the missing controls will help reduce the current risk level, improve compliance with PCI DSS, GDPR, and SOC best practices, and strengthen the overall security posture of the organization.

---

## Disclaimer

This project is based on a fictional scenario from the Google Cybersecurity Certificate and was created for educational and portfolio purposes.
