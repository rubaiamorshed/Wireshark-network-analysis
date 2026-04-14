#  Network Traffic Analysis using Wireshark

## Project Overview

This project focuses on analyzing network traffic from a PCAP file to detect potential cyber threats. The analysis includes identifying malware downloads, command-and-control (C2) communication, and possible data exfiltration.

## Objectives

* Analyze PCAP file using Wireshark
* Detect malware download activity
* Identify C2 communication
* Investigate data exfiltration patterns
* Differentiate between benign and malicious traffic

## Tools Used

* Wireshark
* Network Miner
* Windows VM

## Key Findings

### 1. Malware Download Detection

* Filter used: `http.request.method == "GET" && http.request.uri contains "malware.exe"`
* Source IP: 192.168.0.2
* Destination IP: 192.168.0.1
* HTTP Host: example.com

 Malware was downloaded over HTTP, which is insecure and vulnerable to attacks.

---

### 2. Command & Control (C2) Communication

* Filter used: `tcp.flags.syn == 1 && tcp.port == 4444`
* Observed suspicious TCP communication
* Indicates possible attacker control over infected system

---

### 3. Data Exfiltration

* Filter used: `tcp.port == 8888`
* Payload size: 518 bytes
* Repeated pattern: "XXXXX" (possible obfuscation)

Indicates possible data exfiltration using non-standard port.

---

### 4. Traffic Analysis

* DNS traffic: UDP port 53
* HTTP traffic: Port 80
* Identified normal vs suspicious behavior

---

## Security Insights

* HTTP traffic is not encrypted → vulnerable to MITM attacks
* Malware can be injected during downloads
* Non-standard ports (4444, 8888) often indicate malicious activity

---

## Screenshots



## Conclusion

This analysis demonstrates how network traffic inspection can reveal hidden threats such as malware, C2 communication, and data exfiltration. Tools like Wireshark are essential for network forensics and threat detection.

---

## 👩‍💻 Author

Rubaia Morshed
