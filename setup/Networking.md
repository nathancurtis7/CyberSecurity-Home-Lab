# Lab Networking Configuration

## Purpose
To provide an isolated network environment for safe attack simulation and detection testing.

## Scope
Applies only to the internal home lab network. The home Wi-Fi and personal devices are excluded.

## Environment
- Private RFC1918 subnet (`10.10.10.0/24`)
- Dedicated Ethernet interface
- Managed switch
- Windows host and Linux VM

## Configuration
The lab network is deployed on a logically and physically separate Layer 2 segment from the primary home Wi-Fi environment. Static IP addressing is used for lab hosts to ensure predictable traffic analysis.

## Validation
- Successful ICMP communication between lab hosts
- No routing to the home LAN
- Internet access disabled by default

## Security Considerations
Network isolation prevents attack traffic from impacting personal devices and mirrors enterprise network segmentation practices.

## Notes / Lessons Learned
Static addressing simplified Splunk correlation and PCAP analysis.
