# 🔐 Azure Security Hardening Guide

This repository provides practical steps and visuals to secure Microsoft Azure cloud environments using Microsoft-native services. The goal is to align with Zero Trust principles and Microsoft’s best practices for identity, network, threat detection, and governance.

---

## 🎯 Objective

To demonstrate a real-world approach to hardening an Azure tenant by using tools like Microsoft Defender for Cloud, Azure Policy, and Secure Score to improve cloud security posture and reduce attack surface.

---

## 🧰 Tools Used

- Microsoft Defender for Cloud  
- Azure Secure Score  
- Azure Policy  
- Azure AD Role-Based Access Control (RBAC)  
- Azure Monitor + Log Analytics  
- Microsoft Sentinel (optional)  

---

## ✅ Hardening Checklist

### 🔒 Identity & Access Management
- [x] Enforce MFA via Conditional Access  
- [x] Disable legacy authentication protocols (IMAP, POP3)  
- [x] Assign RBAC roles, avoid direct "Owner" permissions  
- [x] Enable Privileged Identity Management (PIM) for sensitive roles  

### 🌐 Network Security
- [x] Restrict inbound NSG rules — deny public RDP/SSH  
- [x] Enable DDoS Protection (Standard)  
- [x] Use private endpoints for services (e.g., Key Vault, Storage)  

### 🧠 Threat Detection
- [x] Enable Microsoft Defender for all resource types  
- [x] Configure alerts for risky sign-ins, brute-force attempts, lateral movement  
- [x] Use Log Analytics and KQL queries for deeper visibility  

### 🛡 Governance & Compliance
- [x] Enforce tagging, resource locations, and size restrictions using Azure Policy  
- [x] Monitor Secure Score regularly  
- [x] Review compliance initiatives (e.g., ISO 27001, NIST 800-53)  

---

## 📸 Screenshots

### 🔹 Azure Secure Score
![Azure Secure Score](./secure-score.png)

### 🔹 Microsoft Defender for Cloud – Recommendations
![Defender Recommendations](./defender-recommendations.png)

### 🔹 Defender for Cloud Dashboard (No Active Recommendations)
![Defender Dashboard](./defender-dashboard.png)

---

## 🔐 Conditional Access Policy – Configuration Overview

Although this environment does not currently have access to Microsoft Entra ID Premium (required for Conditional Access), the following outlines a typical configuration used in enterprise environments:

#### ✅ Policy: Require MFA for Global Admins

- **Users:** Global Administrator role  
- **Cloud Apps:** All  
- **Conditions:** All locations, all platforms  
- **Access Control:** Require multi-factor authentication (MFA)  
- **Status:** Enabled  

> Conditional Access policies help enforce Zero Trust by controlling access based on user risk, location, and app sensitivity.

---

## 📊 MITRE ATT&CK Mapping

| Tactic            | Technique                  | Tool Used             |
|-------------------|----------------------------|------------------------|
| Initial Access    | T1078 – Valid Accounts     | Conditional Access     |
| Credential Access | T1556 – Auth Process Mod   | Azure AD, Defender     |
| Defense Evasion   | T1562 – Disable Controls   | Defender for Cloud     |

---

## 🧠 Lessons Learned

- Identity is the new perimeter — RBAC and MFA are essential  
- Secure Score helps prioritize what actually reduces risk  
- Azure Policy enforces consistency and prevents drift  
- Defender for Cloud can be a one-stop shop for detection + hardening  

---

## 📫 Contact

Created by Sameer Agha  
📧 sameeragha19@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/in/sameeragha19)
