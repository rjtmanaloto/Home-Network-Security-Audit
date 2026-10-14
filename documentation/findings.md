# Security Findings

## Summary

The audit identified one security concern requiring further investigation, an open Telnet service on the router.

Other observed ports were either associated with expected network services or were filtered and could not be confirmed as active services.

| ID        | Device | Finding                | Severity |         Status |
|-----------|--------|------------------------|----------|----------------|
| Finding-1 | Router | Telnet service exposed | Medium   | Not remediated |

## Finding-1: Telnet Service Exposed

- Severity: Medium
- Device: Router
- Port: 23/tcp
- Service: Telnet
- Evidence: Nmap scan identified TCP port 23 as open and identified the service as Huawei Home Gateway telnetd.
- Risk: Telnet is an older remote access protocol that does not provide the same encryption protections as modern secure remote access protocols.
- Assessment: The Telnet service was detected on the router, but its intended purpose and configuration could not be verified because router administrative access was unavailable.
- Severity Rationale: Medium was assigned because an insecure remote access service was confirmed on the router.
- Recommendation: Verify whether Telnet is required. If it is not required, disable it through the router's administrative interface. If remote administration is required, use a secure alternative supported by the router.
- Remediation Status: Not remediated because router administrative access was unavailable during the audit.

## Limitations

Router administrative access was unavailable during the audit. The assessment was limited by the following:

- Router administrative credentials were unavailable.
- Router configuration could not be directly inspected.
- Only basic Nmap discovery, port scanning, and service identification were performed.
- No exploitation or vulnerability testing was performed.
- Filtered ports could not be confirmed as running services.
- Service versions could not always be identified.
- The assessment only covered devices accessible within the defined local network scope.