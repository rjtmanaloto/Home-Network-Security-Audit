# Home Network Security Audit

## Goal

Conduct a basic security audit of my personal home network and document the results.

## Objectives

- Identify devices and network services exposed on the local network.
- Determine if identified services are expected.
- Document potential security concerns.
- Verify and apply appropriate remediation if possible.

## Workflow

1. Identify the local network.
2. Discover active devices.
3. Perform TCP port scans.
4. Identify network services.
5. Determine whether services are expected.
6. Document security findings.
7. Perform available remediation.
8. Re scan to verify changes.

## Limitations

Router administrative access was unavailable during the audit. The following settings could not be directly verified: 

- Wi-Fi security configuration
- WPS
- Firewall configuration
- UPnP
- Remote administration
- Firmware status
- Port forwarding

## Insights

The audit identified one security concern requiring further investigation, an open Telnet service on the router.

| ID        | Device | Finding                | Severity |         Status |
|-----------|--------|------------------------|----------|----------------|
| Finding-1 | Router | Telnet service exposed | Medium   | Not remediated |

Router administrative access was unavailable during the audit. The service could not be disabled or further investigated.

## Tools Used

- Nmap
- Windows Command Prompt
- Windows PowerShell

## Environments Used

- Windows 10

## Documentation

* [Network Overview](documentation/network_overview.md)
* [Security Audit](documentation/security_audit.md)
* [Security Findings](documentation/findings.md)