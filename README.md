# task-4-firewall-setup
Cyber Security Internship - Task 4: Firewall Setup and Use
​Overview
​This repository contains the documentation, screenshots, and configuration details for Task 4 of the Cyber Security Internship. The objective was to configure, test, and document basic firewall rules on both Windows and Linux operating systems to control network traffic (specifically allowing and blocking traffic).
## Objectives
​Configure basic allow and block firewall rules.
​Gain hands-on experience with Windows Firewall (GUI) and UFW (Uncomplicated Firewall) on Linux.
​Test connectivity using tools like Telnet to validate firewall rules.
​## Tools-Used
Operating system: Windows 
Firewall Tool: Windows Firewall with Advanced Security (GUI/Command Line)
Test utility: telnet
## Execution Steps & Results
​The task was executed by focusing on the core concepts: listing existing rules, creating block rules, testing the block, creating allow rules, and testing the allow rule.
​1. Windows Firewall Configuration & Testing
​The primary focus on Windows was to ensure the ability to control traffic to common ports, specifically using Telnet (Port 23) as the test protocol.
​1.1. Enabling Telnet Client
​The Telnet client is often disabled by default on Windows. I used the Deployment Image Servicing and Management (DISM) tool to enable the feature.
​Command Used: dism /online /Enable-Feature /FeatureName:TelnetClient
Verification (Refer to Screenshot):
The initial attempt failed due to a typo (TalentClient), but the corrected command (TelnetClient) successfully enabled the feature.
​1.2. Testing Connectivity on Port 23 (Telnet)
​With the Telnet Client enabled, a connection test was performed on the local machine (127.0.0.1) to port 23 to observe the default/blocked state.
​Command Used:telnet 127.0.0.1 23
Result (as shown in the uploaded screenshot):
Connecting To 127.0.0.1...Could not open connection to the host, on port 23: Connect failed
​Conclusion: This Connect failed result confirms that traffic on port 23 is currently blocked, either by the default Windows Firewall policy or because no Telnet Server service is listening on that port. This establishes a baseline for further firewall rule testing (i.e., verifying that a new "Allow" rule would then open this connection).
## Key concept Demonstrated
​Through this task, I reinforced my understanding of the following key security concepts:
​Firewall Rules: The hierarchical nature of firewall processing (implicit deny, explicit allow/deny).
​Stateful Inspection: Understanding that both Windows Firewall and UFW are stateful, tracking connection states to allow return traffic automatically.
​Ports and Protocols: The importance of specific port 23 and its corresponding protocols (TCP/UDP) in defining rules.
​Network Diagnostics: Using utilities like telnet to actively test the effectiveness of implemented firewall policies.
​DISM: Using the Deployment Image Servicing and Management tool for Windows feature management.
## Interview Questions
​1. What is a firewall?
A network security device (hardware or software) that monitors and controls incoming and outgoing network traffic based on pre-defined security rules.
​2. Differentiate between stateful and stateless firewall?
Stateful tracks the active state of connections, allowing return traffic automatically. Stateless only examines packets individually based on static rules (source/destination/port).
​3. What are inbound and outbound rules?
Inbound rules govern traffic entering the protected network/system. Outbound rules govern traffic leaving the protected network/system.
​4. Why is UFW (Uncomplicated Firewall) convenient?
It is a user-friendly frontend for managing Linux's complex iptables rules, making configuration much simpler and faster.
​5. Why block port 23 (Telnet)?
Telnet transmits data, including credentials, in plaintext, making it vulnerable to sniffing. Blocking it forces the use of secure alternatives like SSH (port 22).
​6. What are common firewall mistakes?
Overly permissive rules (e.g., "Any to Any"), not using the principle of least privilege, and failing to review and audit rules regularly.
​7. How does a firewall improve network security?
It acts as the first line of defense by enforcing security policy, preventing unauthorized access, blocking malicious traffic (like DoS attacks), and segmenting networks.
​8. What is NAT in firewalls?
Network Address Translation is a process that remaps an IP address space into another, allowing multiple private internal devices to share a single public IP address for external communication.

