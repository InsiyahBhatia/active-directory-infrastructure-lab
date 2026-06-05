# Phase 5: DNS Configuration

DNS was installed as part of the AD DS deployment. In an Active Directory environment, DNS is required because domain controllers, clients, Kerberos, LDAP, and other services rely on DNS records to locate domain resources.

## DNS Role Configuration

DNS configuration details:

- DNS role installed on the Windows Server 2022 domain controller.
- DNS integrated with Active Directory.
- Domain zone created for `corp.local`.
- Domain controller registered service records in DNS.
- Internal clients use the domain controller as their DNS server.

## DNS Resolution Flow

```mermaid
graph LR
    CLIENT[Windows 11 Client] --> QUERY[DNS Query for corp.local]
    QUERY --> DNS[DNS Server on Domain Controller]
    DNS --> ZONE[corp.local Forward Lookup Zone]
    ZONE --> DC[Domain Controller Records]
    DC --> CLIENT
```

## DNS Validation Steps

1. Open Server Manager.
2. Go to `Tools -> DNS`.
3. Expand the server name.
4. Expand `Forward Lookup Zones`.
5. Confirm the `corp.local` zone exists.
6. Review domain records and service records.
7. Confirm the domain controller can resolve its own domain name.

Validation command:

```powershell
Get-ADDomain
```

Expected domain root:

```text
DNSRoot : corp.local
```

Additional validation commands:

```powershell
Resolve-DnsName corp.local
nslookup corp.local
ipconfig /all
```

## Client DNS Requirement

The Windows 11 workstation must use the domain controller as DNS on the internal adapter. If the workstation cannot locate the domain, verify DNS before troubleshooting anything else.

Common DNS checks:

- Confirm the internal adapter has the correct DNS server.
- Confirm the domain controller is reachable.
- Confirm `corp.local` resolves.
- Confirm the DNS zone exists on the server.
- Confirm AD DS and DNS services are running.
