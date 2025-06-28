# DNS & ICMP Packet Analysis

This is a simulated network traffic analysis case study involving DNS resolution failures and ICMP errors. The goal was to investigate a connectivity issue where users were unable to access "www.yummyrecipesforme.com", receiving a "destination port unreachable" error.

I used *tcpdump* to capture packets created when attempting to access the website. DNS queries were sent over UDP to the DNS server, but the responses were ICMP error messages stating that port 53 was unreachable, which means the DNS server wasn't available. m

## Tools Used

- *tcpdump* for live packet capture
- ICMP and UDP protocol analysis
- DNS traffic investigation

## Findings

- UDP packets were sent to *203.0.113.2:53* to resolve "yummyrecipesforme.com"
- Each attempt resulted in an ICMP "port unreachable" error from *203.0.113.2*
- Indicates that the DNS server was not accepting traffic on port 53, so it could have been possibly down or misconfigured

## 📁 Project Contents

- `tcpdump_log.txt`: Raw packet capture from the incident
- `analysis_report.md`: Step-by-step explanation of my investigation

## Skills Demonstrated

- Real-time network traffic capture and inspection
- Interpreting ICMP error messages
- Diagnosing DNS-level connectivity issues
- Writing clear analysis reports for technical audiences

---


