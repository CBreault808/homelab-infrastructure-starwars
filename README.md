# 🚀 Imperial Homelab Fleet Documentation

Welcome to the operational logs of my personal homelab, modeled after the **Imperial Navy from Star Wars**. Each virtual machine (VM) is named after an Imperial vessel, with roles, captains, and missions that simulate real-world IT infrastructure.

This lab environment is designed to help me:

- Prepare for the **CompTIA A+** and other certifications
- Practice system administration, security hardening, and documentation
- Simulate multi-user, multi-node infrastructure with a creative edge
- Develop cybersecurity fundamentals through hands-on experimentation

---

## 🗂️ Fleet Logs (VM-Specific)

| Ship Name      | Folder                                   | Role                                           |
|----------------|-------------------------------------------|------------------------------------------------|
| **Executor**   | [`01_executor`](./01_executor)           | Fleet controller / logging node               |
| **Devastator** | [`02_devastator`](./02_devastator)       | End-user workstation and help desk simulation |
| **Tyrant**     | [`03_tyrant`](./03_tyrant)               | Simulated end-user system used for remote troubleshooting and diagnostics by fleet IT support |


Each ship folder includes:
- `00-overview.md` – specs, mission profile, and captain
- Dated Markdown logs of deployments, updates, and incidents

These serve as living logs for documenting real-world tasks, configuration changes, and troubleshooting steps

---

## 📓 Lab Notes

General-purpose technical notes, test logs, and non-fleet-specific experiments are stored in:

- [Lab Notes](./lab_notes)

Examples might include:
- OS deployment errors (e.g., Devastator's Windows 11 ISO failure)
- Snapshot and backup strategies
- Customization notes (e.g., terminal prompt changes)
- Initial network mapping plans

---

## 🧭 Future Expansion: Red vs. Blue Cyber Lab

This homelab marks the beginning of a larger cybersecurity simulation project:

> ⚔️ **Empire vs. Rebels — Red vs. Blue Battleground**

### Concept Overview:

- **Two physical server racks**, acting as **mini data centers**:
  - 🟥 **Rebel Rack** – simulating Red Team offensive operations
  - 🟦 **Imperial Rack** – simulating Blue Team defensive infrastructure
- Each rack contains multiple server machines representing **fleets**:
  - Each fleet simulates an internal **local network** (LAN)
  - Fleets are connected via a virtual (or physical) **wide area network (WAN)** within each faction
- Each side's WAN is controlled by a **High Command** VM that can:
  - Issue directives
  - Reconfigure fleet routing and security posture
  - Analyze logs and coordinate attacks or defenses

### Long-Term Goal:

- Simulate **offensive vs. defensive cyber scenarios** where Rebel fleets attack and Imperial fleets defend
- Integrate threat detection tools, endpoint protections, and intrusion testing
- Potential use of tools like `Metasploit`, `Zeek`, `Suricata`, and ELK stacks

> 🛠️ This is a long-term vision dependent on future hardware purchases and project milestones.

---

## 🛠️ Technologies Used

This project makes use of:

- **Proxmox VE** – for virtualization and VM management
- **Ubuntu Server/Desktop** – for most fleet nodes
- **GitHub + Markdown** – for documentation and version control
- **Linux tools** – `ufw`, `fail2ban`, `auditd`, `nmap`, and more

---

## 🌌 Thematic Design

This homelab blends **technical skill-building** with **Star Wars lore** to make IT training immersive and engaging. Each fleet, ship, and captain is named to reflect its role in the fictional universe, while also mirroring its technical function in the infrastructure.

> _“The Force will be with you, always.”_ – Obi-Wan Kenobi

