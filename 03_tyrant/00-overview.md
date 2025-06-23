# 🛠️ Ship Profile: ISS Tyrant

**Class:** End-User Simulation VM  
**Role:** Field Unit for Remote Troubleshooting  
**Fleet:** Death Squadron  
**Captain:** Admiral Kendal Ozzel  
**Host Device:** ASUS Vivobook X540U  
**Serial Number:** HBN0GR00X13245C  
**Status:** Operational

---

## 🧾 Specifications

| Component            | Details                              |
|----------------------|--------------------------------------|
| **Operating System** | Windows 10 Home                      |
| **Architecture**     | x64-based PC                         |
| **Processor**        | Intel Core i3-6006U @ 2.00 GHz             |
| **Cores**            | 2                                    |
| **RAM**              | 4 GB (Micron, 2400 MHz)              |
| **Storage**          | 931.5 GB HDD                         |
| **Physical Memory**  | 3,925 MB available                   |

---

## 🎯 Assigned Role

The ISS Tyrant serves as a **guinea pig system** for simulating real-world end-user issues and conducting remote diagnostics from ISS Devastator (Ubuntu help desk VM). It is intended to receive:
- Simulated malfunctions
- Startup bloat
- System slowness
- Troubleshooting scenarios aligned with A+ certification practice

---

## 🧰 Recent Operations

- Recovered from system updates and long boot delay
- Serial number verified via PowerShell (`wmic bios get serialnumber`)
- Initial cleanup performed (disabling startup entries, terminating high-CPU processes)

---

## 🧭 Recommendations

- **RAM Upgrade** to 8 GB if possible for better simulation stability
- **Storage Check** to confirm drive type (HDD vs SSD)
- Maintain regular update checks to avoid hangups during shutdowns
- Assign secondary tasks once stable (e.g. Active Directory join, file access simulation)

---

**Log Folder:** `/logs/tyrant/`  
**Log Maintainer:** Chris Breault

