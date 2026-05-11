\# Security Recommendations - Botium Toys



\## Overview



This document presents security recommendations for Botium Toys based on the internal security audit, risk assessment summary, and controls and compliance checklist.



The objective is to reduce risk, improve compliance, protect sensitive data, and strengthen the overall security posture of the organization.



Botium Toys currently has a high risk score of \*\*8 out of 10\*\*, mainly due to missing controls, weak access management, lack of encryption, lack of backups, and gaps in compliance best practices.



\---



\# Priority Recommendations



\## 1. Implement Least Privilege



Botium Toys should implement the principle of least privilege to ensure that employees only have access to the systems and data required to perform their job responsibilities.



Currently, all employees may be able to access internally stored data, including customer PII/SPII and cardholder data. This increases the risk of unauthorized access, data exposure, misuse, or insider threats.



\### Recommended actions



\- Review current user permissions

\- Restrict access based on job roles and responsibilities

\- Create role-based access groups

\- Limit access to PII/SPII and cardholder data

\- Review permissions regularly



\### Expected benefit



This will reduce confidentiality risks and limit the potential impact of compromised accounts or malicious insiders.



\---



\## 2. Apply Separation of Duties



Botium Toys should implement separation of duties to prevent a single user or department from having too much control over critical processes.



This helps reduce the risk of fraud, misuse, unauthorized changes, and human error.



\### Recommended actions



\- Separate responsibilities for payment processing, data access, approvals, and system administration

\- Ensure critical tasks require review or approval from more than one person

\- Avoid giving one user full control over sensitive workflows

\- Document responsibilities clearly



\### Expected benefit



This will reduce the risk of misuse and improve accountability across business and IT processes.



\---



\## 3. Strengthen Password Policies



Botium Toys should update its password policy to meet current minimum complexity requirements.



Although a password policy exists, its requirements are weak and do not provide sufficient protection against brute force, dictionary attacks, or credential guessing.



\### Recommended actions



\- Require longer passwords

\- Require a combination of letters, numbers, and special characters

\- Prevent the use of common or reused passwords

\- Require password changes when compromise is suspected

\- Educate employees about secure password practices



\### Expected benefit



Stronger password policies will reduce the likelihood of account compromise.



\---



\## 4. Implement a Centralized Password Management System



Botium Toys should deploy a centralized password management system to enforce password requirements and reduce password-related support issues.



Currently, the organization does not have a centralized password management system, which affects both security and productivity.



\### Recommended actions



\- Deploy an enterprise password management solution

\- Enforce password complexity rules centrally

\- Support secure password storage

\- Improve password reset and recovery processes

\- Consider integration with MFA



\### Expected benefit



This will improve password security, reduce password fatigue, and make account management more efficient.



\---



\## 5. Implement Encryption for Sensitive Data



Botium Toys should implement encryption to protect sensitive customer information and cardholder data.



Currently, encryption is not used to protect credit card information that is accepted, processed, transmitted, and stored locally in the company’s internal database.



\### Recommended actions



\- Encrypt credit card data at rest

\- Encrypt data in transit

\- Use secure payment processing methods

\- Review database security configurations

\- Apply encryption to other sensitive data where appropriate



\### Expected benefit



Encryption will help protect confidentiality and reduce the impact of data exposure if systems are compromised.



\---



\## 6. Install an Intrusion Detection System



Botium Toys should implement an intrusion detection system, also known as IDS, to improve its ability to detect suspicious or anomalous activity.



Currently, no IDS is installed.



\### Recommended actions



\- Deploy an IDS to monitor network activity

\- Configure alerts for suspicious behavior

\- Review IDS alerts regularly

\- Integrate alerts with incident response procedures

\- Tune detection rules to reduce false positives



\### Expected benefit



An IDS will improve the organization’s ability to detect potential incidents earlier and respond before the impact becomes more serious.



\---



\## 7. Create Backups of Critical Data



Botium Toys should implement regular backups of critical business data.



Currently, the company does not have backups of critical data, which creates a major business continuity risk.



\### Recommended actions



\- Identify critical data and systems

\- Create a backup schedule

\- Store backups securely

\- Test backup restoration regularly

\- Protect backups from ransomware or unauthorized access



\### Expected benefit



Backups will help the organization recover from data loss, ransomware, hardware failure, human error, or other disruptive incidents.



\---



\## 8. Develop and Test a Disaster Recovery Plan



Botium Toys should create a disaster recovery plan to support business continuity after a major incident.



Currently, there is no disaster recovery plan in place.



\### Recommended actions



\- Identify critical systems and recovery priorities

\- Define recovery time objectives

\- Define recovery point objectives

\- Document recovery procedures

\- Assign recovery roles and responsibilities

\- Test the disaster recovery plan regularly



\### Expected benefit



A disaster recovery plan will help Botium Toys restore operations faster after an incident and reduce downtime.



\---



\## 9. Improve Asset Inventory and Classification



Botium Toys should improve asset identification, classification, and inventory management.



The IT department does not fully know which assets are at risk, which makes it difficult to protect assets properly.



\### Recommended actions



\- Create a complete asset inventory

\- Classify assets based on criticality and sensitivity

\- Identify systems that store or process PII/SPII and cardholder data

\- Review asset ownership

\- Update the inventory regularly



\### Expected benefit



Better asset management will help the organization understand what needs protection and prioritize security efforts more effectively.



\---



\## 10. Improve Access Control Policies



Botium Toys should establish stronger access control policies to define who can access or modify specific data and systems.



Currently, access to internal data is too broad, which creates confidentiality and compliance risks.



\### Recommended actions



\- Define access rules by role and department

\- Limit access to sensitive data

\- Review access rights periodically

\- Remove unnecessary permissions

\- Document access approval processes



\### Expected benefit



Stronger access control policies will help protect PII/SPII, cardholder data, and internal business information.



\---



\## 11. Establish Regular Monitoring and Maintenance for Legacy Systems



Botium Toys should create a regular monitoring and maintenance schedule for legacy systems.



Although legacy systems are monitored and maintained, there is no regular schedule and intervention methods are unclear.



\### Recommended actions



\- Create a maintenance schedule

\- Document intervention procedures

\- Monitor legacy systems for vulnerabilities

\- Plan upgrades or replacement where possible

\- Assign responsibility for legacy system oversight



\### Expected benefit



This will reduce the risk of vulnerabilities in outdated systems being missed or left unresolved.



\---



\# Compliance Recommendations



\## PCI DSS



Botium Toys should prioritize PCI DSS improvements because the company accepts, processes, transmits, and stores credit card information.



\### Recommended actions



\- Restrict access to cardholder data

\- Encrypt credit card information

\- Secure payment transaction touchpoints

\- Implement stronger password management

\- Review payment processing security



\### Expected benefit



These actions will help reduce the risk of cardholder data exposure and improve alignment with PCI DSS best practices.



\---



\## GDPR



Botium Toys should continue improving GDPR-related practices because it conducts business with customers in the European Union.



The company already has a plan to notify E.U. customers within 72 hours if their data is compromised, and privacy policies and procedures are in place. However, E.U. customer data is not fully secured because employees may be able to access PII/SPII unnecessarily.



\### Recommended actions



\- Limit employee access to E.U. customer data

\- Improve classification and inventory of personal data

\- Maintain the 72-hour breach notification process

\- Review privacy policies regularly

\- Ensure personal data is stored and handled securely



\### Expected benefit



These actions will improve the protection of E.U. customer data and reduce the risk of GDPR-related penalties.



\---



\## SOC Type 1 and SOC Type 2



Botium Toys should improve access control and confidentiality practices to better align with SOC expectations.



The company has controls related to data integrity and availability, but access control and confidentiality gaps remain.



\### Recommended actions



\- Establish user access policies

\- Protect PII/SPII from unauthorized access

\- Maintain data integrity controls

\- Maintain availability controls

\- Document access and security processes



\### Expected benefit



These actions will strengthen trust, accountability, and security governance.



\---



\# Implementation Priority



\## High Priority



The following should be addressed first:



1\. Implement least privilege

2\. Restrict access to PII/SPII and cardholder data

3\. Encrypt credit card data

4\. Implement backups of critical data

5\. Create a disaster recovery plan

6\. Install an IDS

7\. Strengthen password policies

8\. Deploy centralized password management



\## Medium Priority



The following should be addressed after the highest-risk gaps:



1\. Improve asset inventory and classification

2\. Establish regular legacy system maintenance

3\. Improve access control documentation

4\. Review compliance documentation

5\. Test incident response and breach notification procedures



\## Existing Controls to Maintain



Botium Toys should continue maintaining the following controls that are already in place:



\- Firewall

\- Antivirus software

\- Locks for offices, storefront, and warehouse

\- CCTV surveillance

\- Fire detection and prevention systems

\- GDPR breach notification plan

\- Privacy policies and procedures

\- Data integrity controls

\- Availability controls



\---



\# Final Recommendation to the IT Manager



Botium Toys should prioritize reducing access-related risks and improving protection for sensitive customer and payment data.



The most urgent actions are to implement least privilege, separation of duties, encryption, IDS, backups, a disaster recovery plan, stronger password policies, and centralized password management.



These improvements will help reduce the current risk level, support compliance with PCI DSS, GDPR, and SOC best practices, and strengthen the organization’s overall security posture.



\---



\## Disclaimer



This project is based on a fictional scenario from the Google Cybersecurity Certificate and was created for educational and portfolio purposes.

