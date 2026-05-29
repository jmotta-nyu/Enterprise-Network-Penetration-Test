# Enterprise Network Penetration Test

## Overview

This project documents a comprehensive black-box penetration test conducted against a simulated enterprise environment consisting of an external web server and an internal network host.

The objective was to identify vulnerabilities, validate attack paths through exploitation, assess business impact, and provide remediation recommendations. The assessment followed methodologies derived from PTES (Penetration Testing Execution Standard), the OWASP Web Security Testing Guide, CVSS, and NIST SP 800-30 risk assessment practices.

## Assessment Scope

### External Infrastructure

* Internet-facing Linux web server
* Web applications
* SSH services
* FTP services
* Staging environment

### Internal Infrastructure

* Linux client workstation
* Internal services accessible through pivoting
* Privilege escalation opportunities
* Credential security assessment

## Methodology

The assessment followed four primary phases:

1. Reconnaissance and Enumeration
2. Vulnerability Identification
3. Exploitation and Privilege Escalation
4. Reporting and Remediation

### Tools Utilized

* Nmap
* Metasploit Framework
* Burp Suite
* SQLMap
* Hydra
* John the Ripper
* OWASP ZAP
* CyberChef

## Attack Path Summary

### External Compromise

1. Enumerated exposed services
2. Identified publicly accessible staging environment
3. Discovered SQL injection vulnerability
4. Extracted user credentials
5. Cracked password hashes
6. Obtained authenticated access
7. Accessed SSH service
8. Retrieved exposed RSA private key
9. Escalated privileges to root

### Internal Network Pivot

1. Established SOCKS proxy through compromised server
2. Enumerated internal host
3. Reused harvested credentials
4. Obtained shell access
5. Identified vulnerable pkexec installation
6. Exploited CVE-2021-4034 (PwnKit)
7. Escalated privileges to root

## Key Findings

| Finding                                        | Risk      |
| ---------------------------------------------- | --------- |
| Exposed RSA Private Key                        | Very High |
| Vulnerable pkexec Installation (CVE-2021-4034) | Very High |
| Public Staging Environment                     | High      |
| SQL Injection Vulnerability                    | High      |
| Weak Password Policy                           | High      |
| Internet-Facing SSH Service                    | Medium    |
| Anonymous FTP Access                           | Medium    |
| Verbose Error Messages                         | Low       |

## Security Impact

Successful exploitation resulted in:

* Root access to the external server
* Root access to the internal workstation
* Credential harvesting and password cracking
* Access to sensitive data
* Lateral movement within the environment
* Complete compromise of critical systems

## Remediation Highlights

Recommended improvements included:

* Removal of exposed private keys
* Migration of staging environments to internal networks
* Parameterized SQL queries and input validation
* Strong password policies
* Restriction of SSH access
* Elimination of anonymous FTP access
* Patch management improvements
* Enhanced logging and monitoring

## Skills Demonstrated

* Penetration Testing
* Vulnerability Assessment
* Web Application Security
* Network Security
* Privilege Escalation
* Credential Attacks
* Risk Assessment
* Security Reporting
* Linux Administration
* Attack Path Analysis
* Security Remediation Planning

## Documentation

A complete professional penetration testing report is included in the `/report` directory.
