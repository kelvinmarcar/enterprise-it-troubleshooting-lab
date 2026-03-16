# Enterprise IT Troubleshooting Lab

Hands-on enterprise troubleshooting lab demonstrating structured incident investigation across Windows and Linux systems in a small business environment.

This lab simulates real-world operational issues that an IT Support Technician or Junior System Administrator may need to diagnose and resolve.

---

## Project Overview

The lab focuses on troubleshooting and resolving:

- Windows client performance issues
- DNS resolution failures
- DHCP service verification
- Remote support through SSH
- Basic security and system health checks

The project was built in a controlled virtual environment to simulate common support and operations tasks in enterprise IT.

---

## Lab Environment

### Infrastructure

- pfSense Firewall – 192.168.10.1
- Windows 11 Client A – 192.168.10.10
- Windows Server 2025 (Domain Controller / DNS / DHCP) – 192.168.10.20
- Ubuntu Server – 192.168.10.30
- Ubuntu Desktop – 192.168.10.40

**Domain:** `lab.local`

---

## Technologies Used

- Windows Server 2025
- Active Directory Domain Services
- DNS
- DHCP
- Windows 11
- Ubuntu Server
- Ubuntu Desktop
- pfSense Firewall
- SSH
- UTM Virtualization

---

## Troubleshooting Scenarios

### 1. Windows Client Performance Issue
Investigated slow system performance and reviewed Task Manager and Event Viewer for diagnostic evidence.

### 2. DNS Resolution Failure
Diagnosed external DNS lookup failures and corrected a client-side IPv6 DNS precedence issue.

### 3. DHCP Service Verification
Reviewed DHCP service state and verified correct lease behavior from the Windows Server.

### 4. Remote Server Support via SSH
Established remote access to Ubuntu Server and verified the SSH service state.

### 5. Security and Final Validation
Confirmed firewall protection and validated the environment after corrective actions.

---

## Key Skills Demonstrated

- Cross-platform troubleshooting (Windows and Linux)
- DNS diagnostics and configuration
- Network connectivity testing
- DHCP verification
- Remote administration via SSH
- Structured troubleshooting methodology
- Basic security validation
- Root cause analysis and verification

---

## Root Cause Example

One key issue identified in the lab was a DNS failure on the Windows client.

**Problem:**  
`nslookup google.com` timed out even though internal systems were reachable.

**Root Cause:**  
The client prioritized an IPv6 link-local DNS address automatically advertised by the gateway, which was not configured to provide DNS resolution.

**Resolution:**  
IPv6 was disabled on the client adapter so DNS queries were directed to the internal Active Directory DNS server (`192.168.10.20`).

This restored external DNS resolution successfully.

---

## Documentation

Full project documentation:

[IT Support Troubleshooting Lab.pdf](documentation/IT%20Support%20Troubleshooting%20Lab.pdf)

---

## Screenshots

### Lab Overview
![Lab Overview](screenshots/01-lab-network-overview.png)

### Windows Performance Troubleshooting
![Task Manager](screenshots/02-windows-slow-performance-task-manager.png)
![Event Viewer](screenshots/03-windows-event-viewer-error-log.png)

### DNS Troubleshooting
![Network Problem](screenshots/04-network-problem-observed.png)
![IPConfig Diagnostics](screenshots/05-ipconfig-diagnostics.png)
![nslookup Failure](screenshots/06-nslookup-failure.png)
![Ubuntu DNS Test](screenshots/07-ubuntu-dns-ping-test.png)
![dig Failure](screenshots/08-dig-command-dns-failure.png)
![DNS Fix](screenshots/09-dns-configuration-fix.png)

### DHCP Verification
![DHCP Service Status](screenshots/10-dhcp-service-status.png)
![DHCP Lease Verification](screenshots/11-dhcp-lease-verification.png)

### Remote Support
![SSH Session](screenshots/12-ssh-remote-support-session.png)
![Linux Service Status](screenshots/13-linux-service-status.png)

### Security and Final Validation
![System Security Check](screenshots/14-system-security-check.png)
![Final Verification](screenshots/15-final-system-verification.png)

---

## Author
Kelvin Jacob Marcar  
ICT Technician | CompTIA Security+ | Active Directory, Microsoft 365, and IT Infrastructure Labs
