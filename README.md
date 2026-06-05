# Active Directory Infrastructure Lab

Designed and deployed a multi-machine enterprise Active Directory environment using Windows Server 2022, Windows 11, and Kali Linux in VirtualBox. This lab focuses on system administration, enterprise networking, DNS, centralized authentication, and domain infrastructure.

The environment simulates a small enterprise network with a Windows Server 2022 domain controller, a Windows 11 domain workstation, and a Kali Linux management VM connected through an isolated internal network with NAT-based internet access.

## Main Objective

Build a realistic enterprise infrastructure foundation for:

- Identity management
- Centralized authentication
- Domain administration
- DNS management
- Enterprise networking
- Future security testing
- Cybersecurity lab development

## Repository Structure

| File | Purpose |
| --- | --- |
| [docs/architecture.md](docs/architecture.md) | High-level topology and domain deployment flow |
| [docs/01-virtual-environment.md](docs/01-virtual-environment.md) | VirtualBox VM creation and resource allocation |
| [docs/02-network-design.md](docs/02-network-design.md) | Internal Network and NAT adapter configuration |
| [docs/03-domain-controller-deployment.md](docs/03-domain-controller-deployment.md) | Windows Server 2022 setup and AD DS role installation |
| [docs/04-domain-creation.md](docs/04-domain-creation.md) | Domain controller promotion and `corp.local` forest creation |
| [docs/05-dns-configuration.md](docs/05-dns-configuration.md) | DNS role setup, domain zone validation, and name resolution checks |
| [docs/06-active-directory-administration.md](docs/06-active-directory-administration.md) | ADUC and ADAC management validation |
| [docs/07-windows-11-workstation.md](docs/07-windows-11-workstation.md) | Windows 11 workstation deployment and domain join process |
| [docs/08-kali-linux-management-vm.md](docs/08-kali-linux-management-vm.md) | Kali Linux installation and network validation |
| [docs/09-infrastructure-validation.md](docs/09-infrastructure-validation.md) | End-to-end validation checklist and commands |
| [docs/screenshot-evidence.md](docs/screenshot-evidence.md) | Screenshot references grouped by evidence area |

## Lab Summary

| System | Role | Resources |
| --- | --- | --- |
| Windows Server 2022 | Domain controller for `corp.local` | 4 GB RAM, 2 CPUs, 60 GB storage |
| Windows 11 Pro | Enterprise workstation | 4 GB RAM, 2 CPUs, 60 GB storage |
| Kali Linux | Linux management and testing VM | 4 GB RAM, 2 CPUs, 40 GB storage |

## Domain Configuration

| Setting | Value |
| --- | --- |
| Domain name | `corp.local` |
| NetBIOS name | `CORP` |
| Server role | Domain Controller |
| AD role | Active Directory Domain Services |
| DNS role | Installed with AD DS |
| Forest type | New forest |

## Core Technologies

| Technology | Purpose |
| --- | --- |
| Windows Server 2022 | Domain controller |
| Active Directory Domain Services | Identity management and domain authentication |
| DNS Server | Internal name resolution |
| Windows 11 Pro | Enterprise workstation |
| Kali Linux | Linux management and testing system |
| VirtualBox | Virtualization platform |
| PowerShell | Windows administration and validation |
| Active Directory Users and Computers | User, computer, and group management |
| Active Directory Administrative Center | Modern AD administration |

## Skills Demonstrated

- Windows Server 2022 administration
- Active Directory deployment
- DNS configuration
- Enterprise identity management
- Windows 11 administration
- Linux administration
- PowerShell administration
- VirtualBox virtualization
- Network architecture design
- Infrastructure deployment
- System administration
- Enterprise networking

## Future Enhancements

This repository can serve as the foundation for future infrastructure and security-focused projects:

- Active Directory attack lab
- BloodHound enumeration lab
- Splunk detection lab
- Sysmon monitoring lab
- Kerberos security lab
- SOC analyst detection lab
