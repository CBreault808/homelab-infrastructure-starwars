# 🛠️ After-Action Report: Executor – Active Directory Deployment

**Date:** 2025-06-27  
**VM:** Executor  
**OS:** Ubuntu Server LTS  
**Function:** Samba Active Directory Domain Controller  
**Fleet:** Death Squadron  
**Domain:** deathsquadron.local
**Snapshot Created:** `executor-ad-setup-complete`

**Fleet SysAdmin:** CBreault808


---

## 🎯 Mission Objective

Deploy and configure the `Executor` VM as the centralized Domain Controller for the Death Squadron fleet. Simulate crew personnel assignment across starship departments using a Star Wars-themed naming convention, organize users under proper Organizational Units (OUs), and establish a maintainable AD structure for future expansion.

---

## ✅ Summary of Tasks

### 🧩 Domain Setup
- Installed and configured Samba with internal DNS backend.
- Joined the domain `deathsquadron.local`.
- Key settings:
  - **Hostname:** `executor`
  - **FQDN:** `executor.deathsquadron.local`
  - **NetBIOS Name:** `DEATHSQUADRON`
  - **DNS Forwarder:** (configured locally)
- Kerberos authentication initialized and verified.
- Domain SID confirmed post-provisioning.

---

### 🗂️ Organizational Unit Structure

Created the following OU hierarchy under `OU=Executor,DC=deathsquadron,DC=local`:

- `OU=BridgeCrew`
- `OU=Engineering`
- `OU=Admin`
- `OU=Weapons`
- `OU=FighterWing`

These simulate departmental roles aboard the fleet’s command ship.

> **Note:** OU nesting verified via CLI using `ldbsearch`. While not visualized like a GUI, the DN format reflects correct AD structure.

---

### 👥 User Creation and Assignment

#### Account Format
- Usernames: `firstname.lastname`
- Email format: `firstname.lastname@executor.deathsquadron.local`

#### Method
Accounts were created using:

```bash
sudo samba-tool user create <username>
```
> **Note:** Attempting to use commas (e.g. `valrik,deen`) caused the following error:
> `failed to add user invalid dn (null)`
> This has been logged as a learning reference for scripting and command input safety.

#### Department Heads:
- BridgeCrew - `valrik.deen`
- Engineering - `mira.voss`
- Admin - `talon.korr`
- Weapons - `saela.renn`
- FighterWing - `thane.drel`

#### Assignment to Departments:
Used `ldbrename` to move users from default `CN=Users` to their respective department OUs:
```bash
sudo ldbrename -H /var/lib/samba/private/sam.ldb \ "CN=username,CN=Users,DC=deathsquadron,DC=local" \ "CN=username,OU=Department,OU=Executor,DC=deathsquadron,DC=local"
```
Confirmed successful for all 25 users using terminal-based inspection and output checks.

---

## 💡 Insights and Breakthroughs

- **CLI vs GUI Understanding:**  
  Initially assumed the CLI output would resemble GUI tree views (like in Active Directory Users & Computers). Realized that Distinguished Names (DNs) such as `OU=BridgeCrew,OU=Executor,...` accurately represent a nested structure, even if it's not visually indented. This clarified confusion about AD structure when viewed from the terminal.

- **LDAP Editing Approaches:**  
  Using `ldbedit` was difficult at first due to unfamiliar editor behavior. Although possible to edit DN entries manually, it proved easier and safer to use `ldbrename` to move users between OUs. This method ensured that user entries retained integrity without malformed saves.

- **SSH Connection Troubleshooting:**  
  Experienced connection refusal when trying to SSH into the Executor VM. Resolved by:
  - Verifying the correct IP address (Executor VM, not Proxmox host)
  - Ensuring `sshd` was listening on port 22
  - Using `ping` and `ss` to confirm network and service availability

- **Manual Work vs Scripting Efficiency:**  
  While manually adding users was time-consuming, it served as valuable practice for building Linux and Samba muscle memory. Future deployments would benefit from Bash or Python scripting to automate user creation and OU assignment, especially as the fleet expands.

---

## 🛡️ Snapshot Details

-**Snapshot created after final verification of user structure and OU assignment:**

Name: `executor-ad-setup-complete`
  
State: Clean shutdown
  
Purpose: Rollback point before Mailcow or any AD expansion
  
Tool: Proxmox web GUI > Snapshots > Create Snapshot

---

## 📌 Next Steps

-**Install and configure Mailcow on the Executor VM**

-**Intergrate the AD-based user emails using the custom domain**

-**Begin user creation and AD integration for the Devastator help desk VM crew**




  
