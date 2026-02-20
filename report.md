# Corporate Exposure Assessment: Walmart.com
**Date:** February 20, 2026  
**Analyst:** Brandon J. (JonesB101)  
**Project:** OSINT Portfolio Case Study  

---

## 1. Executive Summary
This assessment provides a comprehensive overview of the external attack surface for **walmart.com**. Using passive reconnaissance techniques, I identified significant infrastructure assets, social footprints, and potential metadata leakage. The findings indicate a mature security posture regarding server hardening (e.g., no exposed RDP), but highlight opportunities for improvement in document metadata scrubbing and monitoring developer-centric social presence.

## 2. Objective & Scope
The goal of this project was to perform an unauthorized (passive) assessment of Walmart's public digital footprint to identify:
* Subdomains and IP infrastructure.
* Public-facing services and vulnerabilities (via Shodan).
* Corporate social identities and developer exposure.
* Sensitive internal information leaked via document metadata.

**Scope:** Limited to `*.walmart.com` and associated corporate social handles.

## 3. Methodology & Tools
I followed the standard OSINT lifecycle (Collection, Processing, Analysis). No active scanning (Nmap/Burp Suite) was performed to maintain a passive footprint.
* **Infrastructure Mapping:** Amass, theHarvester.
* **Service Enumeration:** Shodan CLI.
* **Identity Intelligence:** Sherlock.
* **Metadata Analysis:** ExifTool.

## 4. Key Findings

### 4.1 Infrastructure and Services
* **Total Assets:** Over 465,000 indexed records identified via Shodan.
* **Security Strength:** Zero instances of Port 3389 (RDP) were found, suggesting robust remote-access policies.
* **Development Exposure:** Multiple QA and Staging subdomains identified (e.g., `advertising.staging.walmart.com`).

### 4.2 Social Footprint & Identity
* **Walmart-Labs:** Over 211 associated accounts found. Developer presence on platforms like GitHub and Slack represents a high-priority area for potential credential or code leakage.

### 4.3 Metadata Leakage
* **File Analyzed:** `FY2025-Walmart-ESG-Report.pdf`
* **Exposure:** Identified internal workstation naming patterns and specific versions of PDF production software, which could assist in tailoring a spear-phishing campaign.

## 5. Recommendations
1.  **Metadata Scrubbing:** Implement automated tools to strip metadata from all publicly hosted PDF and Office documents.
2.  **Shadow IT Monitoring:** Regularly audit social accounts under corporate naming conventions (e.g., `walmart-labs`) to ensure they comply with security policies.
3.  **Staging Hardening:** Ensure all `*.staging` subdomains are behind authentication or IP-restricted to prevent pre-release feature leakage.

---
*Disclaimer: This report is for educational purposes as part of a cybersecurity portfolio at Columbia Southern University.*
