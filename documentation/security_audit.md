# Security Audit

## Workflow/Methodology

The audit was performed from my Windows laptop connected to my home network.

The assessment focused on:

- Host discovery
- Device identification
- Basic TCP port scanning
- Service identification
- Identification and assessment of network services

No exploitation, password attacks, or denial-of-service testing was performed.

## Host Discovery

Nmap was used to identify active hosts on the local network.

- Command used:
    - `nmap -sn [REDACTED]`

## Port Scan

Basic port scans were performed on my devices: Router, Smartphone, and Laptop.

### Results

| Device     | Port     | State    | Service      | Expected?   | Notes | 
|------------|---------:|----------|--------------|-------------|-------|
| Router     | 21/tcp   | filtered | ftp          | Unknown     | Service not confirmed since port is filtered. |
| Router     | 22/tcp   | filtered | ssh          | Unknown     | Service not confirmed since port is filtered. |
| Router     | 23/tcp   | open     | telnet       | Investigate | Nmap service detection identified the service as Huawei Home Gateway telnetd. |
| Router     | 53/tcp   | open     | domain       | Yes         | Nmap service detection identified the service as DNS. |
| Router     | 80/tcp   | filtered | http         | Unknown     | Service not confirmed since port is filtered. |
| Router     | 8022/tcp | filtered | oa-system    | Unknown     | Service not confirmed since port is filtered. |
| Smartphone | 5060/tcp | filtered | sip          | Unknown     | Service not confirmed since port is filtered. |
| Laptop     | 135/tcp  | open     | msrpc        | Yes         | Nmap service detection identified the service as Microsoft Windows RPC. |
| Laptop     | 139/tcp  | open     | netbios-ssn  | Yes         | Nmap service detection identified the service as Microsoft Windows netbios-ssn. |
| Laptop     | 445/tcp  | open     | microsoft-ds | Yes         | Nmap service detection identified the service as Microsoft-DS, but could not determine the specific version. |

## Observations

- The Nmap scan identified several open and filtered TCP ports on the scanned devices.
- The router had TCP port 23 open and was identified as running Telnet. This service requires further investigation because Telnet is an older remote access protocol and was not confirmed as a service intentionally required by the network.
- The router had TCP port 53 open and was identified as a DNS service. Nmap received a generic `SERVFAIL` response during service detection. No security issue was concluded from this response alone.
- The router had TCP ports 21, 22, 80, and 8022 in a filtered state. Because these ports were filtered, the FTP, SSH, HTTP, and OA-System services could not be confirmed. 
- The smartphone had TCP port 5060 in a filtered state. Because it is filtered, the SIP service could not be confirmed.
- The laptop had TCP ports 135 and 139 open and was identified as Microsoft Windows RPC and Microsoft Windows netbios-ssn. These ports are associated with Windows networking services. 
- The laptop had TCP port 445 open and was identified as Microsoft-DS. The specific service version could not be determined.
- No exploitation, password attacks, or attempts to bypass authentication were performed. The audit was limited to network discovery, port scanning, and basic service identification.

## Limitations

Router administrative access was unavailable during the audit. The following settings could not be directly verified: 

- Wi-Fi security configuration
- WPS
- Firewall configuration
- UPnP
- Remote administration
- Firmware status
- Port forwarding