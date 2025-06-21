# ISS Devastator – End User Virtual Machine

## 🛠️ Purpose
An Ubuntu Desktop VM acting as a typical end-user machine in the fleet. Used for troubleshooting, help desk simulation, and end-user support scenarios.

## 🧰 Operating System
- Ubuntu Desktop 22.04.4 LTS

## 💻 Proxmox VM Settings
- BIOS: OVMF (UEFI)
- Disk: qcow2, 60GB, on local storage
- RAM: 4GB
- Cores: 2 vCPUs
- TPM: Removed for snapshot compatibility
- Snapshots: `barebones-ubuntu-install`

## 🧪 Installed Tools
- htop
- net-tools
- nmap
- remmina
- wireshark
- bleachbit
- timeshift
- neofetch

## 📸 Snapshot Strategy
Snapshot taken after OS install and updates for clean restore point.

## 🛠️ Troubleshooting Notes
- TPM must be removed to enable snapshots.
- Ensure ISO is detached before snapshotting.
- Use UEFI (OVMF) for modern Linux/Windows VMs.
