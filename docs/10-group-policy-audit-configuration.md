# Group Policy Audit Policy Configuration

Configured advanced audit policies on the `corp.local` domain controller to enable comprehensive security logging and monitoring.

## Audit Policies Configured

| Policy | Setting | Purpose |
| --- | --- | --- |
| Audit Credential Validation | Success and Failure | Track authentication attempts |
| Audit Kerberos Authentication Service | Success and Failure | Monitor Kerberos ticket requests |
| Audit Kerberos Service Ticket Operations | Success and Failure | Track Kerberos service access |
| Audit Account Lockout | Success and Failure | Detect brute-force lockouts |
| Audit Logon | Success and Failure | Track user logon events |
| Audit Logoff | Success | Track user logoff events |
| Audit Directory Service Access | Success and Failure | Monitor AD object access |
| Audit Directory Service Changes | Success and Failure | Track AD object modifications |
| Audit Process Creation | Success | Track process execution |
| Audit Sensitive Privilege Use | Success and Failure | Monitor privilege escalation |
| Audit Kernel Object | Success and Failure | Track kernel object access |
| Audit System Integrity | Success and Failure | Monitor system health |
| PowerShell Script Block Logging | Enabled | Log PowerShell command execution |

## Implementation Steps

1. Opened Group Policy Management on the domain controller
2. Edited the Default Domain Controllers Policy
3. Navigated to Computer Configuration > Policies > Windows Settings > Security Settings > Advanced Audit Policy Configuration
4. Enabled audit policies across all categories:
   - Account Logon
   - Account Management
   - Detailed Tracking
   - DS Access
   - Logon/Logoff
   - Object Access
   - Policy Change
   - Privilege Use
   - System
5. Enabled PowerShell Script Block Logging for command auditing
6. Ran `gpupdate /force` to apply policies immediately

## Verification

Applied policies using `gpupdate /force` and confirmed both Computer and User Policy updates completed successfully.

## Screenshots

See [screenshot-evidence.md](screenshot-evidence.md) for visual documentation of the audit policy configuration.
