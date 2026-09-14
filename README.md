# CYB 220 – Network Security

Coursework from **CYB 220: Network Security** at Southern New Hampshire University. This repo collects the hands-on labs and written projects I completed, covering network sandboxing in GNS3 and Cisco Packet Tracer, Windows host hardening with Group Policy, host- and network-based firewalls, ACLs, network segmentation, and evaluating intrusion detection/prevention technologies.

**Tools used:** GNS3 · Cisco Packet Tracer · VMware Workstation · Windows 10 / Windows Server 2016 · Cisco IOS · Local Group Policy Editor

---

## Labs & Activities

### 1-2 · Packet Tracer Setup Activity
Initial setup and verification of Cisco Packet Tracer with a basic PC topology.
📄 ![1-2 Packet Tracer Setup](https://github.com/andree-salvo/CYB-220-Network-Security/blob/0930eeba636377811bfc340599137ee35a46ac8c/CYB%20220%201-2%20Packet%20Tracer%20Setup%20Activity.pdf)



### 2-4 · GNS3 Sandboxing Part One
Built a three-segment network in GNS3: two Windows 10 PCs, a Windows Server, and a Cisco 3745 router. Configured static IPs and gateways on each host, brought up and addressed the router interfaces (`fa0/0`, `fa0/1`, `fa1/0`) via IOS CLI, then verified end-to-end connectivity with ping tests between every host and gateway.
📄 `CYB_220_2-4_Activity_-_GNS3_Sandboxing_Part_One.pdf`

### 3-2 · GNS3 Sandboxing Part Two
Hardened a Windows VM using the Local Group Policy Editor. Mapped the full GPO path for each required policy and applied it, with screenshot evidence:
- Hide specified Control Panel items
- Remove Task Manager
- Remove Recycle Bin icon from desktop
- Disable delete notifications on all volumes
- Turn off printing over HTTP
- Turn on Internet Explorer menu bar by default

📄 `CYB_220_3-2_Activity_-_GNS3_Sandboxing_Part_Two.pdf`

### 4-3 · Module Four Activity – Firewalls & ACLs
Packet Tracer lab working through layered traffic filtering:
- **Host-based firewall** on an FTP server: default-deny inbound rule, then an allow rule scoped to the End_User subnet using a wildcard mask
- **Standard named ACL** (`officeFTP`) created, applied outbound on `g6/0`, then edited in place to fix a deny-all ordering problem
- **Extended ACL** on a remote router permitting only SMTP/POP3 from a kiosk host to the mail server, verified by sending mail and confirming the file server was blocked

📄 `CYB_220_4-3_Activity_Worksheet.pdf`

---

## Projects

### Project One · Virtual Systems and Networking Concept Brief (5-3)
Configured a small GNS3 environment to spec and justified the use of virtualization.
- **Group Policy hardening:** interactive logon warning banner, minimum password length of 8, prevent changing desktop background, audit logon events (success/failure), forced lock-screen image, Windows Defender Firewall profile
- **Network setup:** router interface addressing, static IPs on three kiosk PCs, an admin PC, and a domain server
- **Written analysis:** benefits and drawbacks of virtualization for sandboxing, and virtual disaster recovery as another use case

📄 `CYB_220_5-3_Project_One_Submission_-_Virtual_Systems_and_Networking_Concept_Brief.pdf`

### Project Two · Network Segmentation Strategy (6-2)
Segmented a Packet Tracer network so that only the admin subnet can reach the FTP server and only the kiosk can reach the web server.
- Host-based firewall rule on the FTP server limiting inbound traffic to the admin network
- FTP accounts configured with least privilege (read/list for standard users, full rights for the admin account)
- Extended ACL on the office router permitting the kiosk host to the web server on port 80 only
- Rationale tying each control to segmentation and least privilege

📄 `CYB_220_6-2_Network_Segmentation_Strategy_Project_Two.pdf`

### Project Three Milestone · Prioritizing Evaluation Criteria (5-2)
Completed a technology evaluation criteria table (effectiveness and cost factors) against an organizational security plan scenario, then prioritized the top three criteria (false positives, network effects, time) and mapped them to two fundamental security design principles: **defense in depth** and **least privilege**.
📄 `CYB_220_5-2_Project_Three_Milestone_Prioritizing_Evaluation_Criteria.pdf`

### Project Three · Evaluation of Network Protection Technologies (7-2)
Recommendation report for a financial institution with a small IT team and a preference for open-source tooling. Applied defense in depth to recommend a combined **NIDS + NIPS** approach using tools like Snort, Suricata, and Wazuh, outlined required resources (dedicated sensor hardware, staffing, an incident response plan), and framed the recommendation with an adversarial mindset.
📄 `CYB_220_7-2__Evaluation_of_Netwrok_Protection_Technologies_Project.pdf`

---

## Skills Demonstrated
- Network topology design and IP addressing in GNS3 and Packet Tracer
- Cisco IOS interface configuration and troubleshooting
- Standard and extended ACLs (numbered vs. named, inbound vs. outbound placement, wildcard masks)
- Host-based firewall rule design and default-deny posture
- Windows hardening via Group Policy
- Network segmentation and least-privilege access design
- Evaluating and recommending IDS/IPS solutions against organizational constraints
