# 🛰️ Mission Log 001 – SSH Protocol Installation

**Mission Date:** 2025-06-22  
**Vessel:** ISS Tyrant  
**Fleet:** Death Squadron  
**Captain:** Admiral Kendal Ozzel  
**Initiated From:** Local Console (Vivobook)  
**Mission Status:** ✅ Success

---

## 🎯 Objective

Establish an OpenSSH server on ISS Tyrant to allow for remote administrative access and integration into Death Squadron’s troubleshooting framework. Tyrant is to act as a simulated end-user system, with remote monitoring and diagnostics performed by ISS Devastator.

---

## ⚠️ Initial Conditions

- System: Windows 10 Home  
- Issue: `sshd` service not present or recognized  
- Attempts to install OpenSSH via standard `Add-WindowsCapability` failed due to system limitations or partial package corruption  
- `Start-Service sshd` and `Get-Service` commands failed due to missing service

---

## 🧰 Actions Taken

- Verified system was online and responding
- Attempted standard installation method:

  ```powershell
  Add-WindowsCapability -Online -Name OpenSSH.Server
  ```

  → *Failed (service not found after install)*

- **Advanced recovery attempt made using `DISM`** (Deployment Image Servicing and Management):

  ```powershell
  DISM /Online /Add-Capability /CapabilityName:OpenSSH.Server~~~~0.0.1.0
  ```

  ✅ *This command successfully forced the installation of the OpenSSH server.*

- Service created manually:

  ```powershell
  sc create sshd binPath= "C:\Windows\System32\OpenSSH\sshd.exe" start= auto
  ```

- Service verified and started:

  ```powershell
  Get-Service sshd
  Start-Service sshd
  ```

- Confirmed listening state:

  ```powershell
  netstat -a | findstr 22
  ```

- Successfully connected remotely from ISS Devastator

---

## ✅ Outcome

OpenSSH server installed and operational. ISS Tyrant now accepts SSH connections from fleet command for monitoring and troubleshooting. This installation required aggressive but controlled remediation using advanced tools (`DISM` and `sc`) to overcome system limitations.

---

## 🧠 Notes

- The use of `DISM` for package repair or installation is considered an advanced method and may be useful in A+ and real-world environments where GUI-based or traditional tools fail.
- Tyrant is now fully integrated into the lab’s remote management network.

---

**Mission Logged By:** CBreault808  
**Log Folder:** `/logs/tyrant/`
