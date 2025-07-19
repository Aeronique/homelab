# AeroLab v1.0: Building a Personal Cybersecurity Homelab

I am actively working toward a career in cybersecurity, with a strong focus on blue team roles such as SOC Analyst, Digital Forensics and Incident Response (DFIR), or Threat Intelligence. As someone transitioning into the field, building this homelab has become a core part of how I develop hands-on skills, reinforce what I learn, and demonstrate my commitment to continuous growth.

When I first began exploring the idea of a homelab, I felt overwhelmed—not knowing where to start, how to structure it, or what to do once it was built. After weeks of research, one piece of advice stood out: once you begin building your lab, you won’t want to stop. That has proven entirely accurate.

Over the past two months, I’ve developed **AeroLab v1.0**, a personal cybersecurity lab designed to support hands-on learning, technical experimentation, and practical application of cybersecurity concepts. What began with a pair of refurbished machines has evolved into a structured, scalable environment for continuous professional development.

---

## Table of Contents

- [Hardware Overview](#hardware-overview)  
- [Virtualization Stack & Current VMs](#virtualization-stack--current-vms)  
- [Planned Enhancements](#planned-enhancements)  
- [Technical Objectives & Use Cases](#technical-objectives--use-cases)  
- [Conclusion](#conclusion)  
- [Author](#author)  

---

## Hardware Overview

The lab runs on two **Lenovo ThinkCentre M920q** USFF nodes—compact, quiet, and enterprise-grade at a budget price. Both were purchased used (Windows 11 Pro, 8 GB RAM, 256 GB SSD), wiped, and re-provisioned with Proxmox VE.

- **Node 1**: Upgraded to 64 GB RAM for resource-intensive VMs  
- **Node 2**: Stock RAM + spare parts for lighter workloads & utility services  
- **Clustered** via Proxmox for centralized management & resource scheduling  
- Administered remotely from a Lenovo T14 ThinkPad  
- Total cost so far: **~\$300 USD** (hardware + upgrades)

![AeroLab Network Layout](images/aerolab-network-layout.png)  
*High-level network layout across VLANs, managed via clustered Proxmox nodes.*

---

## Virtualization Stack & Current VMs

AeroLab simulates an enterprise environment with segmented VLANs. Current deployments:

- **pfSense** *(planned dedicated node)*  
  Enterprise-grade firewall for routing, VLAN segmentation & traffic filtering  
- **Kali Linux**  
  Reconnaissance, vulnerability scanning & pen-testing  
- **Wazuh (Server & Agents)**  
  SIEM: log aggregation, file-integrity monitoring & rule-based alerting  
- **Ubuntu + Suricata**  
  Network-based IDS monitoring internal traffic  
- **Windows Server 2025 (DC)**  
  Active Directory, DNS & file-sharing  
- **Windows 11 Workstation**  
  Domain-joined client for endpoint visibility & GPO testing  
- **Docker Host + Portainer**  
  Containerized apps: DVWA, bWAPP, WebGoat for attack/defense exercises  
- **Pi-hole** *(planned)*  
  DNS-based ad/tracker blocking alongside pfSense  

Each VM is provisioned with resource limits and strict network rules to reinforce segmentation, least privilege, and defense-in-depth.

---

## Planned Enhancements

To extend functionality and realism:

- Deploy a **Lenovo M720q** dedicated to pfSense/OPNsense + Pi-hole + Suricata IDS/IPS  
- Install a low-profile GPU for local AI/ML experiments and media streaming  
- Upgrade both nodes with 2.5 GbE NICs for higher throughput on the UniFi Flex Mini 2.5G switch  
- Add a dedicated **NAS** for centralized file storage (media, logs, snapshots, backups)  
- Rack everything in a **GeekPi 8U** setup with proper cable management & airflow  
- Integrate a **Raspberry Pi** touchscreen for local dashboards & health monitoring  
- Implement cooling fans with temperature sensors, a UPS, PDU, and patch panel for reliability  

---

## Technical Objectives & Use Cases

AeroLab supports:

- VM provisioning & hypervisor management  
- VLAN-based network segmentation & firewall rule enforcement  
- Centralized log collection & event correlation via Wazuh  
- Simulated attacker behavior with Suricata + SIEM for detection validation  
- Windows domain administration & Group Policy configuration  
- Endpoint visibility & host-based logging  
- Container orchestration (Docker + Portainer) for vulnerable app testing  
- Basic incident response workflows & threat emulation  

---

## Conclusion

AeroLab v1.0 is my cornerstone for hands-on cybersecurity learning—an evolving lab where I can break things, troubleshoot errors, and build real-world readiness. Future versions will refine the architecture, add new services, and introduce more advanced testing scenarios.

---

## Author

**Aeronique**  
Former educator, current Soldier, aspiring Threat Intelligence / DFIR / Blue Team cybersecurity professional  
https://medium.com/@aeronique
