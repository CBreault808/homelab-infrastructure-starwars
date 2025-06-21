# 🧑‍💻 Devastator User Management Log

**VM Name:** Devastator  
**OS:** Ubuntu Desktop 22.04.4 LTS  
**Date:** 2025-06-21  
**Captain:** Wullf Yularen

---

## 🎯 Objective

Simulate a realistic end-user workstation scenario by creating a named user profile with associated metadata, and customizing the terminal environment to reflect a unique ship + captain identity.

---

## 🔧 Actions Performed

- Created a new Linux user:
  ```bash
  sudo adduser yularen
Simulated adding user metadata
-Room Number
-Work Phone
-Home Phone

Switched user via Terminal using the following command:
su - yularen

Customized shell prompt to reflect new user:
yularen@devastator:~$

NOTES: Consider using the command "sudo usermod -c "Captain Wullf Yularen"" to add a comment field to the user profile. This VM can be used in the future to sumulate end-user permissions, trouble tickets, and role based
access in future help desk labs
