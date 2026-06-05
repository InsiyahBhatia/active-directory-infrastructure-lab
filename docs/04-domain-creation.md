# Phase 4: Domain Creation

After AD DS was installed, the server was promoted to a domain controller. The lab uses a new Active Directory forest because this is a standalone enterprise environment.

## Domain Details

| Setting | Value |
| --- | --- |
| Root domain name | `corp.local` |
| NetBIOS name | `CORP` |
| Deployment type | New forest |
| DNS integration | Enabled |
| Global Catalog | Enabled |

## Domain Controller Promotion

Promotion path:

```text
Server Manager -> Notifications -> Promote this server to a domain controller
```

Deployment option:

```text
Add a new forest
```

Root domain name:

```text
corp.local
```

Promotion configuration steps:

1. Select `Add a new forest`.
2. Enter `corp.local` as the root domain name.
3. Select the forest and domain functional level supported by Windows Server 2022.
4. Keep `DNS Server` selected.
5. Keep `Global Catalog` selected for the first domain controller.
6. Enter and confirm the DSRM password.
7. Confirm the NetBIOS name as `CORP`.
8. Review database, log, and SYSVOL paths.
9. Run the prerequisite checks.
10. Start the promotion.
11. Allow the server to restart after promotion.
12. Sign in using the domain administrator context after reboot.

After promotion, the server became the domain controller for `corp.local`. It now provides directory services, domain authentication, DNS records for the domain, and centralized identity management.
