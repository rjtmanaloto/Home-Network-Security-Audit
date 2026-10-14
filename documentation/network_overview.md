# Network Overview

## Network Information

| Information     | Value      |
|-----------------|------------|
| IPv4 Address    | [REDACTED] |
| Subnet Mask     | [REDACTED] |
| Default Gateway | [REDACTED] |
| Network Range   | [REDACTED] |

## Gateway Connectivity

- Gateway reachable: Yes
- Ping result: 4 replies
    - Pinging [REDACTED] with 32 bytes of data:
        - Reply from [REDACTED]: bytes=32 time=3ms TTL=64
        - Reply from [REDACTED]: bytes=32 time=5ms TTL=64
        - Reply from [REDACTED]: bytes=32 time=3ms TTL=64
        - Reply from [REDACTED]: bytes=32 time=6ms TTL=64
- Average response time: 
    - Minimum = 3ms
    - Maximum = 6ms
    - Average = 4ms

## ARP Table

| Internet Address |Physical Address |Type    |
|------------------|-----------------|--------|
| [REDACTED]       |[REDACTED]       |dynamic |
| [REDACTED]       |[REDACTED]       |static  |
| [REDACTED]       |[REDACTED]       |static  |
| [REDACTED]       |[REDACTED]       |static  |
| [REDACTED]       |[REDACTED]       |static  |
| [REDACTED]       |[REDACTED]       |static  |
| [REDACTED]       |[REDACTED]       |static  |

## Known Devices

| Device      | Type              | Connection |
|-------------|-------------------|------------|
| Router      | Networking Device | Wi-Fi      |
| Laptop      | Computer          | Wi-Fi      |
| Smartphone  | Phone             | Wi-Fi      |

## Network Diagram

```
               Internet
                  │
                  │
            ┌───────────┐
            │   Router  │
            └─────┬─────┘
                  │
        ┌─────────┼─────────┐
        │                   │
     Laptop             Smartphone
```

## Notes

The network information was collected from my Windows laptop connected to my home network.

## Limitations

Router administrative access was unavailable during the audit. Router configuration settings were not assessed.