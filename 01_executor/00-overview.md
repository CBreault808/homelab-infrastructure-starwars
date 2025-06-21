# 🧠 Executor – Fleet Controller Node

**VM Name:** Executor  
**OS:** Ubuntu Server 24.04.2 LTS  
**Hostname:** executor  
**Captain:** Admiral Piett  
**Role:** Central logging and fleet monitoring server  
**Deployment Date:** 2025-06-20  

---

## 🎯 Mission Profile

The Executor serves as the **Fleet Controller** of the homelab, simulating a centralized Linux server for fleet-wide security monitoring, log analysis, and Linux administration tasks.

It is also used for:
- Practicing system hardening
- Managing firewall rules (UFW)
- Deploying Fail2Ban and Auditd
- Running SSH for remote access
- Logging and user auditing

---

## ⚙️ Configuration Snapshot

| Setting       | Value                   |
|---------------|--------------------------|
| CPU           | 2 cores                  |
| RAM           | 2 GB                     |
| Disk          | 35 GB                    |
| Network       | Bridged (vmbr0)          |
| Installed Tools | OpenSSH, UFW, Fail2Ban, Auditd |

---

## 🛠️ Planned Enhancements

- Add log centralization or monitoring stack (e.g., syslog-ng or Graylog)
- Create log forwarding from other VMs
- Implement basic service health checks

---

## 📂 Sub-Logs

- `2025-06-20-initial-deployment.md` _(coming soon)_
- `2025-06-22-firewall-testing.md` _(planned)_

