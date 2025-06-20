# Windows 11 Installation Troubleshooting on Proxmox

## 🚫 Problem
Proxmox VM refused to install Windows 11 Pro, citing system requirements not met:
- No TPM
- No Secure Boot
- Unsupported CPU generation

## 🛠️ Attempted Fixes
- Added TPM storage in VM hardware
- Switched to UEFI BIOS
- Patched Windows 11 ISO using Rufus with:
  - TPM 2.0 bypass
  - Secure Boot bypass
  - Online Account requirement bypass

## 🔁 Issues Encountered
- Looping reboots after setup errors
- Setup wiping registry edits after reboots
- Boot errors with patched ISO (`Boot0003`, `NBP` errors)

## ✅ Next Action
- Postponed Windows 11 install for *Devastator*
- Installed Ubuntu Desktop instead as temporary OS
