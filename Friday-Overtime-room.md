# 🕵️ TryHackMe: Friday Overtime – Lab Notes

---

## 📋 Objective
Simulate a SOC investigation of suspicious activity on a Friday evening. Use Splunk to identify what happened, when, and how.

---

## 🔍 Investigation Summary

- Alerts triggered for unusual activity from internal host `DESKTOP-XXXXX`.
- Search narrowed using `index=main` and filtering on `host`, `source`, and `EventCode`.
- Identified use of `PowerShell` to download an executable from a suspicious URL.
- Found encoded commands indicating obfuscation attempts.
- Observed persistence mechanisms and lateral movement.

---

## 🧠 Commands & Filters Used

```spl
index=main EventCode=4104 OR EventCode=4688
index=main "powershell" OR ".exe"
index=main sourcetype=WinEventLog* CommandLine=*
