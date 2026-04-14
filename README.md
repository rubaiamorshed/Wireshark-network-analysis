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

<img width="886" height="716" alt="Screenshot 2025-03-16 162713" src="https://github.com/user-attachments/assets/87a1b1c9-4c68-43f7-aeab-60a28d0328b8" />
<img width="876" height="729" alt="Screenshot 2025-03-16 162437" src="https://github.com/user-attachments/assets/1474052e-bb9a-434b-b9f2-51253ca351c9" />
<img width="873" height="710" alt="Screenshot 2025-03-16 162359" src="https://github.com/user-attachments/assets/fb282976-fdc1-4e67-91ec-8d4d385e9cc7" />
<img width="900" height="716" alt="Screenshot 2025-03-16 162247" src="https://github.com/user-attachments/assets/2d22305c-b365-438d-8a9d-23573fc6a50d" />
<img width="885" height="718" alt="Screenshot 2025-03-16 162136" src="https://github.com/user-attachments/assets/939ef9d7-14f2-4c20-9fe8-02c3ed0b2a7e" />
<img width="864" height="721" alt="Screenshot 2025-03-16 162032" src="https://github.com/user-attachments/assets/203bc6e5-0141-4a33-9bae-6be8649483ac" />
<img width="880" height="720" alt="Screenshot 2025-03-16 161936" src="https://github.com/user-attachments/assets/7a86ff54-94a1-4fd5-b0f3-b60d5ab68836" />
<img width="873" height="713" alt="Screenshot 2025-03-16 161909" src="https://github.com/user-attachments/assets/6b0b6502-8b83-4fa9-8a03-75219e47b985" />
<img width="881" height="711" alt="Screenshot 2025-03-16 161857" src="https://github.com/user-attachments/assets/c8686005-cef7-422d-83c4-22b36e7e8af9" />
<img width="885" height="732" alt="Screenshot 2025-03-16 161344" src="https://github.com/user-attachments/assets/0f0ef69e-a888-4e3d-8eef-dbd860420d23" />
<img width="887" height="718" alt="Screenshot 2025-03-16 161303" src="https://github.com/user-attachments/assets/b1931f02-30e6-409c-b750-90a65debfff2" />
<img width="893" height="715" alt="Screenshot 2025-03-16 161231" src="https://github.com/user-attachments/assets/e3bfe347-e349-46f1-af2c-ab5210ec2a9f" />
<img width="888" height="722" alt="Screenshot 2025-03-16 161215" src="https://github.com/user-attachments/assets/13b93c81-e8b4-4c77-9d65-0d428b84ce9a" />
<img width="884" height="710" alt="Screenshot 2025-03-16 161154" src="https://github.com/user-attachments/assets/cae3dc37-a93d-4a52-928f-17bb315f80e1" />
<img width="891" height="716" alt="Screenshot 2025-03-16 160852" src="https://github.com/user-attachments/assets/5792fdd4-2bc0-4d24-97eb-78e6904068ab" />
<img width="883" height="726" alt="Screenshot 2025-03-16 160331" src="https://github.com/user-attachments/assets/5186e837-f01b-4140-a754-07ed4ce81b78" />
<img width="860" height="713" alt="Screenshot 2025-03-16 160226" src="https://github.com/user-attachments/assets/55e59142-9791-4ee7-8e90-e279cb5bd10a" />
<img width="869" height="712" alt="Screenshot 2025-03-16 155356" src="https://github.com/user-attachments/assets/f8d2fd49-ba56-464d-be4e-f31d46213e70" />
<img width="891" height="730" alt="Screenshot 2025-03-16 154530" src="https://github.com/user-attachments/assets/88638985-6f57-4f22-8153-bcfb37b6f315" />
<img width="872" height="723" alt="Screenshot 2025-03-16 154422" src="https://github.com/user-attachments/assets/c3a3cdd4-e87f-4765-b301-4b80c9f022bc" />
<img width="865" height="723" alt="Screenshot 2025-03-16 154129" src="https://github.com/user-attachments/assets/1b39673c-c98a-4701-9d05-83fab2466c13" />
<img width="896" height="724" alt="Screenshot 2025-03-16 153949" src="https://github.com/user-attachments/assets/942d58e2-8f8e-4b78-832a-1379d405d464" />
<img width="868" height="718" alt="Screenshot 2025-03-16 153518" src="https://github.com/user-attachments/assets/dad7c933-1c33-4c13-b494-750b624cf798" />
<img width="904" height="714" alt="Screenshot 2025-03-16 153149" src="https://github.com/user-attachments/assets/09218435-5c90-48ee-ab6d-82de344a8e53" />
<img width="861" height="714" alt="Screenshot 2025-03-16 153055" src="https://github.com/user-attachments/assets/111321d7-26ad-4c72-8c70-a9f6513deb1f" />
<img width="862" height="721" alt="Screenshot 2025-03-16 152903" src="https://github.com/user-attachments/assets/53c0d894-4a5f-4dcf-8cb3-5b454e35518b" />
<img width="873" height="727" alt="Screenshot 2025-03-16 152854" src="https://github.com/user-attachments/assets/585b4811-79d5-4bc5-b793-acda33e30c3f" />
<img width="863" height="726" alt="Screenshot 2025-03-16 152811" src="https://github.com/user-attachments/assets/47799b80-3d23-4fa3-8b2e-185e7535015f" />
<img width="868" height="716" alt="Screenshot 2025-03-16 152758" src="https://github.com/user-attachments/assets/dcf16612-549a-481e-91e0-fe6e6bb33383" />
<img width="871" height="725" alt="Screenshot 2025-03-16 152747" src="https://github.com/user-attachments/assets/3fb62e59-ae34-4562-9871-6ac28effda40" />
<img width="870" height="718" alt="Screenshot 2025-03-16 152600" src="https://github.com/user-attachments/assets/d2070853-f65b-4e58-816f-e2e3a3eaa6c9" />
<img width="861" height="718" alt="Screenshot 2025-03-16 151525" src="https://github.com/user-attachments/assets/2bffa843-3c5d-4ba1-b42f-5813cc3f1c33" />
<img width="879" height="717" alt="Screenshot 2025-03-16 151349" src="https://github.com/user-attachments/assets/cd723bfa-80ab-4eaf-aca4-9cb686cbde7b" />
<img width="861" height="726" alt="Screenshot 2025-03-16 151010" src="https://github.com/user-attachments/assets/43e065b6-d00f-4daf-81cc-187df9213c81" />
<img width="830" height="719" alt="Screenshot 2025-03-16 150909" src="https://github.com/user-attachments/assets/2fd9e1fb-0e7e-425e-b299-014bb731ce54" />


## Conclusion

This analysis demonstrates how network traffic inspection can reveal hidden threats such as malware, C2 communication, and data exfiltration. Tools like Wireshark are essential for network forensics and threat detection.

---

## Author

Rubaia Morshed
