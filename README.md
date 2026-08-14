# Cloud Security Engineering Portfolio

Hands-on cloud security engineering projects focused on Microsoft Azure, Microsoft Entra ID, Microsoft Defender for Cloud, Microsoft Sentinel, KQL, identity security, detection engineering, threat hunting, and incident response.

This repository demonstrates practical implementation of cloud security controls across identity, infrastructure, data protection, security monitoring, and security operations. The projects are aligned with real-world Azure security engineering responsibilities and the Microsoft SC-500: Cloud and AI Security Engineer Associate security domains.

---

## About This Portfolio

The objective of this repository is to demonstrate hands-on cloud security engineering capabilities beyond certification knowledge.

The labs document the design, implementation, testing, and validation of Azure security controls including:

- Identity and access management
- Zero Trust security controls
- Least-privilege access
- Cloud security posture management
- Secrets and key management
- Security logging and monitoring
- SIEM implementation
- KQL threat hunting
- Detection engineering
- Security incident investigation
- Incident response
- Cloud governance and compliance

Each project includes technical documentation and supporting evidence demonstrating the security control or investigation performed.

---

# Core Security Technologies

| Security Area | Technologies |
|---|---|
| Cloud Platform | Microsoft Azure |
| Identity & Access | Microsoft Entra ID, Azure RBAC |
| Zero Trust | Conditional Access, MFA, Identity Protection |
| Cloud Security | Microsoft Defender for Cloud |
| Secrets Management | Azure Key Vault |
| SIEM | Microsoft Sentinel |
| Security Operations | Microsoft Defender |
| Log Management | Azure Monitor, Log Analytics |
| Threat Hunting | Kusto Query Language (KQL) |
| Detection Engineering | Microsoft Sentinel Analytics Rules |
| Incident Response | Microsoft Sentinel / Defender Incidents |
| Governance | Azure Policy, Regulatory Compliance |

---

# Identity & Access Security

Hands-on implementation of identity security controls using Microsoft Entra ID and Azure RBAC.

Security concepts demonstrated include:

- Role-Based Access Control (RBAC)
- Least-privilege access
- Azure role assignments
- Custom security roles
- Conditional Access policies
- Multi-Factor Authentication (MFA)
- Identity risk controls
- Microsoft Entra Identity Protection
- Privileged access concepts
- Zero Trust access principles

These labs demonstrate how identity controls can be implemented to reduce unauthorized access and limit the impact of compromised accounts.

---

# Cloud Security Posture Management

Microsoft Defender for Cloud was used to assess and improve the security posture of Azure resources.

Hands-on activities include:

- Microsoft Defender for Cloud configuration
- Cloud security posture assessment
- Security recommendation analysis
- Secure Score review
- Resource security recommendations
- Regulatory compliance monitoring
- Cloud workload protection concepts
- Security control remediation

These projects demonstrate practical experience identifying and addressing cloud security posture weaknesses.

---

# Secrets & Key Management

Azure Key Vault was used to implement secure storage and management of sensitive application secrets.

Security controls demonstrated include:

- Azure Key Vault deployment
- Secret creation and management
- RBAC-based Key Vault access
- Least-privilege secret access
- Secret lifecycle management
- Diagnostic logging
- Security monitoring
- Audit analysis using KQL

This demonstrates practical implementation of secure secrets management within Azure environments.

---

# 🔎 Microsoft Sentinel SIEM & Detection Engineering

Microsoft Sentinel was configured as a cloud-native SIEM to collect and analyze Azure security telemetry.

A complete detection pipeline was implemented:

**Azure Resource Activity → Azure Activity Logs → Diagnostic Settings → Log Analytics → KQL → Microsoft Sentinel → Analytics Rule → Alert → Incident**

Hands-on activities include:

- Log Analytics workspace configuration
- Azure Activity Log ingestion
- Diagnostic settings configuration
- Microsoft Sentinel deployment
- Custom KQL security queries
- Scheduled analytics rules
- MITRE ATT&CK mapping
- Security alert generation
- Incident creation

---

# Threat Hunting with KQL

Microsoft Sentinel Advanced Hunting and Kusto Query Language were used to proactively investigate Azure administrative activity.

Threat hunting activities included:

- Establishing Azure Activity baselines
- Identifying successful resource modifications
- Hunting Azure `WRITE` operations
- Profiling administrative activity by user
- Aggregating security events
- Analyzing operation frequency
- Investigating Sentinel configuration changes
- Detecting modifications to analytics rules
- Capturing correlation IDs for investigation

Example hunting logic:

```kusto
AzureActivity
| where ActivityStatusValue == "Success"
| where OperationNameValue contains "WRITE"
| project TimeGenerated,
          OperationNameValue,
          ActivityStatusValue,
          ResourceGroup,
          Caller,
          ResourceId
| sort by TimeGenerated desc
```

These investigations demonstrate how cloud telemetry can be queried and analyzed to identify potentially suspicious administrative behavior.

---

# Security Incident Investigation & Response

Microsoft Sentinel and Microsoft Defender were used to investigate security incidents generated from Azure resource activity.

The incident-response workflow demonstrated:

**Detection → Alert → Incident → Investigation → Analysis → Classification → Resolution**

Hands-on activities included:

- Reviewing Sentinel incidents
- Alert triage
- Azure Activity Log analysis
- Caller investigation
- Resource modification analysis
- Detection validation
- Incident classification
- Analyst documentation
- Benign-positive determination
- Incident resolution

Authorized test activity was intentionally generated to validate that the detection pipeline successfully identified Azure resource modifications.

The resulting incidents were investigated and classified based on the underlying activity.

---

# Featured Security Projects

## Microsoft Sentinel Detection Engineering

Built a Microsoft Sentinel detection workflow capable of identifying successful Azure resource modifications.

Implemented:

- Azure Activity Log ingestion
- Log Analytics integration
- KQL detection logic
- Scheduled analytics rule
- MITRE ATT&CK mapping
- Alert generation
- Automatic incident creation

---

## Microsoft Sentinel Threat Hunting

Performed proactive security investigations using KQL against Azure Activity Logs.

Investigated:

- Administrative WRITE operations
- Resource modifications
- User activity patterns
- Sentinel configuration changes
- Analytics rule modifications

---

## Microsoft Sentinel Incident Response

Performed end-to-end security incident triage and investigation.

Workflow:

**Azure Resource Change → Telemetry → Detection → Alert → Incident → Investigation → Classification → Resolution**

---

## Azure Identity & Zero Trust Security

Implemented identity and access security controls using Microsoft Entra ID.

Controls included:

- Azure RBAC
- Least privilege
- Conditional Access
- MFA
- Identity risk policies
- Identity Protection

---

## Azure Key Vault Security

Implemented secure secrets management and monitoring using Azure Key Vault.

Demonstrated:

- Secrets management
- RBAC
- Access control
- Logging
- Auditing
- KQL investigation

---

## Microsoft Defender for Cloud

Evaluated Azure cloud security posture using Microsoft Defender for Cloud.

Demonstrated:

- Security recommendations
- Secure Score
- CSPM
- Regulatory compliance
- Security remediation

---

# Security Skills Demonstrated

### Cloud Security Engineering

- Microsoft Azure security
- Cloud security architecture
- Cloud security posture management (CSPM)
- Azure resource security
- Security configuration validation

### Identity Security

- Microsoft Entra ID
- Azure RBAC
- Conditional Access
- MFA
- Identity Protection
- Least privilege
- Zero Trust

### Security Operations

- Microsoft Sentinel
- Microsoft Defender
- SIEM monitoring
- Security alert triage
- Incident investigation
- Incident response
- Threat hunting

### Detection Engineering

- KQL
- Azure Activity Log analysis
- Custom analytics rules
- Detection logic
- Security telemetry analysis
- MITRE ATT&CK mapping

### Data & Secrets Security

- Azure Key Vault
- Secret management
- RBAC-based access
- Security logging
- Audit monitoring

### Governance

- Azure security recommendations
- Regulatory compliance
- Cloud governance
- Security posture assessment

---

# 📂 Lab Portfolio

## Identity Security

Projects covering Microsoft Entra ID, RBAC, Conditional Access, MFA, Identity Protection, and least-privilege security controls.

## Defender for Cloud

Projects covering Azure security posture management, security recommendations, Secure Score, and regulatory compliance.

## Key Vault Security

Projects covering secrets management, RBAC, diagnostic logging, and security monitoring.

## Microsoft Sentinel

### Lab 08 – SIEM Threat Detection

Configured Azure Activity Log ingestion, developed KQL detection logic, and created a custom Microsoft Sentinel analytics rule that generated security incidents from Azure resource modifications.

### Lab 09 – Threat Hunting

Performed proactive threat hunting using KQL to investigate Azure administrative operations, resource modifications, user behavior, and Sentinel configuration changes.

### Lab 10 – Incident Investigation & Response

Investigated a Microsoft Sentinel security incident from detection through triage, evidence analysis, classification, documentation, and resolution.

### Lab 11 – Azure Security Governance

Azure Policy, security governance, compliance enforcement, and cloud security control validation.

### Lab 12 – Azure Cloud Security Capstone

End-to-end Azure security engineering project integrating identity security, cloud security posture management, secrets protection, logging, detection engineering, threat hunting, and incident response.

---

# Certifications

### Microsoft Certified: Cloud and AI Security Engineer Associate (SC-500)

Hands-on security engineering knowledge across Microsoft cloud security technologies including identity, infrastructure, applications, data, AI workloads, security operations, and cloud security posture management.

### Microsoft Certified: Azure Fundamentals (AZ-900)

Foundational knowledge of Microsoft Azure cloud services, architecture, governance, security, and management.

### CompTIA Security+

Foundational cybersecurity knowledge covering security operations, threats, vulnerabilities, architecture, identity, risk management, and incident response.

---

# Education & Professional Development

**B.S. – Technology Leadership & Innovation Management**  
University of Houston

---

# Career Focus

**Cloud Security Engineer | Azure Security Engineer | Security Engineer**

Primary technical interests:

- Azure Cloud Security
- Identity Security
- Zero Trust
- Cloud Security Posture Management
- Detection Engineering
- Microsoft Sentinel
- KQL Threat Hunting
- Security Operations
- Incident Response
- AI & Cloud Security

---

# Portfolio Goal

The purpose of this repository is to continuously develop and demonstrate practical cloud security engineering capabilities through hands-on implementation.

Rather than focusing solely on theoretical certification concepts, these projects demonstrate the ability to configure security controls, analyze cloud telemetry, develop detections, investigate suspicious activity, and respond to security incidents within Microsoft Azure environments.
