 DNS & ICMP Traffic Analysis Report

**Author:** Paul Harrison  
**Date:** 06/28/2025 
**Primary Tool Used:** `tcpdump`  
**Target Domain:** `www.yummyrecipesforme.com`  
**DNS Server IP:** `203.0.113.2`  
**Client IP:** `192.51.100.15`

--
#### Objective
- Determine why users were receiving error **"Destination port unreachable"** when trying to access 'www.yummyrecipesforme.com'
-----

This objective was completed using 'tcpdump' to analyze packet-level traffic between my browser and the DNS server. 

The UDP protocol was used to contact the DNS server. The UDP packets were sent from the client to the DNS server @ IP 203.0.113.2 on port 53 to resolve
the domain name www.yummyrecipesforme.com. This is based on the results of the network analysis, showing that the ICMP echo reply returned the error
'"udp port 53 unreachable"'. The port noted that that error message is used for DNS srrvices on UDP port 53. So, the most likely
issue is that the DNS server was unreachable on port 53, probably because the DNS service was misconfigured/down, or even blocked by a firewall.

The first signs of this issue were at 1:24 PM, indicated by the UDP DNS requests on the tcpdumb logs. In troubleshooting, I tried to 
access the wbesite myself and received the same error. This is when I used tcpdump to monitor network traffic during thi sprocess.
I observed DNS queries being sent to 203.0.113.2 over UDP, each being met with the same ICMP error.

