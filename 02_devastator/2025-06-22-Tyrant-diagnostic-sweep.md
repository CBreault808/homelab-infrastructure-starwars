# 🛰️ Remote Mission Log: Diagnostic Sweep – ISS Tyrant

**Mission Date:** 2025-06-22  
**Remote Host:** ISS Tyrant  
**Initiated From:** ISS Devastator  
**Commanding Sysadmin:** CBreault808  
**Target OS:** Windows 10 Home  
**Specs (partial):** 4 GB RAM, ASUS Vivobook, Intel i3 8265NGW chipset

---

## 🎯 Objective:
Remotely identify and mitigate system performance issues on ISS Tyrant using Devastator’s SSH terminal. The goal was to simulate real-world help desk support for an end-user-class vessel.

---

## 🔍 Observations:

- **Severe system lag and slow response times**
- **High CPU usage from non-essential services**
- **Limited free RAM (~500 MB at scan time)**
- **Startup process cluttered with duplicate entries and Microsoft services**

---

## 🧪 Actions Taken:

- Connected to ISS Tyrant from Devastator via SSH (OpenSSH)
- Executed remote diagnostics using PowerShell
- Identified `OfficeClickToRun.exe` as CPU bottleneck and safely terminated it
- Confirmed `MsMpEng.exe` (Windows Defender) running normally; left intact
- Inspected memory availability: 3.8 GB total, ~0.49 GB free
- Analyzed startup programs:
  - Disabled `MicrosoftEdgeAutoLaunch` via registry
  - Disabled `OneDrive` autostart via registry
  - Attempts to disable OneDrive setup tasks failed (access denied)
- Forced system shutdown after Windows denied a standard shutdown due to "other users" (confirmed to be a false positive)

---

## ✅ Outcome:

- CPU and memory usage improved post-optimization
- Remote connection maintained throughout operation
- Mission objectives met
- System pending physical RAM upgrade for long-term stability

---

## 📌 Notes:

- ISS Devastator is confirmed operational as the fleet’s primary help desk and sysadmin vessel
- ISS Tyrant will receive its own log and overview file in a dedicated folder following hardware spec review

---

**Mission Status:** ✅ Success  
**Next Action:** Create `logs/tyrant/` directory with `overview.md` and system baseline after hardware analysis
