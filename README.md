# Network Traffic Attack Analysis

## Project Overview
This project analyzes captured network traffic to identify reconnaissance, lateral movement, brute-force attacks, and data exfiltration within an internal network.

# Architecture Diagram - Network Traffic Attack Analysis

        ┌──────────────────────────────────────┐
        │        Compromised Host               │
        │        192.168.2.111                  │
        │  Attacker Pivot / Internal Recon      │
        └───────────────┬──────────────────────┘
                        │
        ┌───────────────▼──────────────────────┐
        │        Internal Network Segment       │
        │                                      │
        │  ┌──────────────┐   ┌─────────────┐ │
        │  │  SSH Target  │   │ FTP Server  │ │
        │  │192.168.2.77  │   │192.168.2.108│ │
        │  └──────────────┘   └─────────────┘ │
        │                                      │
        └───────────────┬──────────────────────┘
                        │
                 PCAP Capture Files
                        │
        ┌───────────────▼──────────────────────┐
        │          Analyst Workstation          │
        │              Wireshark                │
        │   Timeline Reconstruction and IOC     │
        └──────────────────────────────────────┘



## Environment and Data
- Multiple PCAP files
- Internal enterprise network traffic
- Suspected compromised host acting as attacker pivot

## Security Objectives
- Identify malicious behavior in packet captures
- Reconstruct attack timelines
- Confirm successful compromise and data exfiltration
- Propose mitigation strategies

## Tools and Technologies
- Wireshark
- TCP stream analysis
- Protocol inspection (SSH, FTP, ARP)
- PCAP forensic techniques

## Key Tasks Performed
- Identified SSH reconnaissance attempts
- Detected lateral movement via port scanning
- Confirmed FTP brute-force attack
- Verified successful authentication using weak credentials
- Identified file retrieval and data exfiltration
- Correlated activity across multiple capture files

## Attack Evidence
- SSH connection attempts across multiple hosts
- Sustained FTP login failures followed by success
- FTP RETR commands confirming data theft
- Clear command-and-response sequences

## Outcomes and Lessons Learned
- Demonstrated full attack lifecycle from access to exfiltration
- Highlighted risks of weak credentials
- Emphasized need for segmentation and monitoring
- Reinforced importance of protocol-level analysis

## Skills Demonstrated
- Network traffic analysis
- Incident investigation
- Attack reconstruction
- Forensic evidence reporting
