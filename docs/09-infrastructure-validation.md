# Phase 9: Infrastructure Validation

After deploying the Windows Server 2022 domain controller, Windows 11 workstation, and Kali Linux management VM, validation tests were performed to ensure proper Active Directory functionality, DNS operation, and network connectivity.

## Domain Validation

Run on the domain controller:

```powershell
Get-ADDomain
```

This confirms that Active Directory is available and that the server recognizes the `corp.local` domain.

## Windows 11 Validation

Run on Windows Server 2022 and Windows 11:

```cmd
ipconfig
ipconfig /all
```

This confirms that Windows systems have the expected network adapters and DNS configuration.

## Kali Linux Validation

Run on Kali Linux:

```bash
ip a
ip route
```

This confirms that Kali has active network interfaces and routing.

## Validation Results

| Component | Status |
| --- | --- |
| Active Directory | Complete |
| DNS | Complete |
| Windows 11 networking | Complete |
| Kali networking | Complete |
| Internal network connectivity | Complete |
| Internet connectivity | Complete |
