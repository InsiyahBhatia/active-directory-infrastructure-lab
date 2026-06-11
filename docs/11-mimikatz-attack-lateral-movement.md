# Mimikatz Credential Dumping and Lateral Movement Attack

Performed a Mimikatz credential dumping + lateral movement attack on the `corp.local` Active Directory lab from Kali Linux, then configured detection/hardening on the domain controller.

## Attack Chain Summary

```
Reconnaissance
     ↓
SMB enumeration (NetExec --shares)
     ↓
Credential validation (corp.org\winuser:Pass!321 → Pwn3d!)
     ↓
Mimikatz deployment via SMB put-file to Windows\Temp\
     ↓
Local admin group confirmed on target
     ↓
Detection: GPO audit policies configured (Kerberos, Privilege Use,
           Process Creation, PowerShell Script Block Logging)
```

## Phase 1 — Detection and Audit Policy Setup (Domain Controller)

Configured advanced audit policies on the domain controller to enable comprehensive security logging and monitoring before/after the attack.

### Audit Policies Configured

| Policy | Setting | Purpose |
| --- | --- | --- |
| Audit Kerberos Service Ticket Operations | Success and Failure | Detect Kerberoasting (Event ID 4769) |
| Audit Sensitive Privilege Use | Success and Failure | Detect SeDebugPrivilege usage by Mimikatz (Event ID 4673) |
| Audit Process Creation | Success | Detect new process spawning (Event ID 4688) |
| Audit Account Lockout | Success and Failure | Detect brute-force lockouts |
| Audit Logon | Success and Failure | Track user logon events |
| Audit Directory Service Changes | Success and Failure | Track AD object modifications |
| Audit Kernel Object | Success and Failure | Monitor kernel object access |
| PowerShell Script Block Logging | Enabled | Capture all PowerShell commands including obfuscated |

### GPO Configuration Screenshots

- **27** — Audit Kerberos Service Ticket Operations
- **28** — Audit Kernel Object
- **29** — Audit Sensitive Privilege Use
- **30** — Audit Directory Service Changes
- **31** — Audit Account Lockout and Logon
- **32** — Audit Process Creation
- **33** — Audit Kerberos Overview
- **34** — gpupdate /force success
- **35** — PowerShell Script Block Logging enabled
- **36** — Audit Sensitive Privilege Use review

## Phase 2 — The Attack (from Kali Linux)

### Step 1: Local Admin Group Validation

Confirmed `winuser` is in the local Administrators group on the Windows 11 workstation, validating the compromised account has admin rights needed for Mimikatz execution.

**Screenshot 37** — `net localgroup administrators` output

### Step 2: Credential Validation

Confirmed `corp.org\winuser:Pass!321` — **[Pwn3d!]** — full admin access on CENTRAL-SRV (Windows Server 2022 Domain Controller).

**Screenshot 38** — NetExec Pwn3d admin access confirmed

## MITRE ATT&CK Mapping

| Technique ID | Technique | Evidence |
| --- | --- | --- |
| T1078 | Valid Accounts | `winuser:Pass!321` credentials |
| T1021.002 | SMB/Windows Admin Shares | Lateral movement via SMB |
| T1003 | OS Credential Dumping | Mimikatz deployment to Windows\Temp |
| T1059.001 | PowerShell | Script Block Logging configured to detect |

## Key Event IDs for Detection

| Event ID | Description | Trigger |
| --- | --- | --- |
| 4673 | Sensitive Privilege Use | Mimikatz SeDebugPrivilege |
| 4688 | Process Creation | Mimikatz.exe execution |
| 4769 | Kerberos Service Ticket | Kerberoasting |
| 4624 | Logon Success | Credential validation |
| 4625 | Logon Failure | Failed attempts |

## Screenshots

See [screenshot-evidence.md](screenshot-evidence.md) for visual documentation of the complete attack chain.
