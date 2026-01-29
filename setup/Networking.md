## Network Segmentation

The home lab is deployed on a logically and physically separate network from my home WiFi network.
The lab network operates on an isolated Layer 2 segment using a dedicated Ethernet interface and switch, preventing direct traffic flow between the lab environment and my home WiFi network.
IP addresses are configured within a private RFC1918 range (`10.10.10.0/24` for example) and does not route to the home LAN.
Any connectivity to external networks (e.g. updates or tool downloads) is explicitly controlled and enabled only when required.

This segmentation ensures:
- Containment of attack simulations and malicious traffic
- No exposure of personal devices to lab activity
- Realistic enterprise-style network isolation
