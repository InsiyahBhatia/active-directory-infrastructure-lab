# Screenshot Evidence

Screenshots are stored in the [`../screenshots`](../screenshots) directory.

The screenshots document the lab build process, AD DS deployment, DNS validation, Windows workstation configuration, Kali Linux networking, Active Directory administration tools, security hardening, and the Mimikatz credential dumping attack.

## AD DS, DNS, and Domain Validation

### ADUC corp.local Overview

![ADUC corp.local overview](../screenshots/01-aduc-corp-local-overview.png)

### PowerShell Get-ADDomain Summary

![PowerShell Get-ADDomain summary](../screenshots/02-powershell-get-addomain-summary.png)

### PowerShell DNSRoot Validation

![PowerShell DNSRoot validation](../screenshots/03-powershell-dnsroot-validation.png)

### ADUC Domain Containers

![ADUC domain containers](../screenshots/04-aduc-domain-containers.png)

### Domain Controller ipconfig

![Domain controller ipconfig](../screenshots/05-domain-controller-ipconfig.png)

## Server Manager Role Installation and Promotion

### Role Installation Progress

![Server Manager role installation progress](../screenshots/06-server-manager-role-install-progress.png)

### AD DS and DNS Installation Results

![Server Manager AD DS and DNS installation results](../screenshots/07-server-manager-ad-ds-dns-install-results.png)

### Server Manager Domain Overview

![Server Manager domain overview](../screenshots/15-server-manager-domain-overview.png)

## Windows 11 Setup and Workstation Configuration

### Windows 11 System About

![Windows 11 system about](../screenshots/13-windows-11-system-about.png)

### Windows 11 Domain Join Settings

![Windows 11 domain join settings](../screenshots/14-windows-11-domain-join-settings.png)

### Windows 11 Account Settings

![Windows 11 account settings](../screenshots/16-windows-11-account-settings.png)

## Kali Linux Network and Terminal Validation

### Kali Network Interface Configuration File

![Kali network interface configuration file](../screenshots/09-kali-network-interface-config-file.png)

### Kali Network Connections List

![Kali network connections list](../screenshots/10-kali-network-connections-list.png)

### Kali Ethernet Connection Settings

![Kali ethernet connection settings](../screenshots/11-kali-ethernet-connection-settings.png)

### Kali DNS Server Setting

![Kali DNS server setting](../screenshots/12-kali-dns-server-setting.png)

### Kali IP Address Output

![Kali IP address output](../screenshots/17-kali-ip-address-output.png)

### Kali Hostname and IP Output

![Kali hostname and IP output](../screenshots/18-kali-hostname-and-ip-output.png)

### Kali Network Resolution Checks

![Kali network resolution checks](../screenshots/19-kali-network-resolution-checks.png)

### Kali Interface Validation

![Kali interface validation](../screenshots/20-kali-interface-validation.png)

### Kali Package Installation Output

![Kali package installation output](../screenshots/21-kali-package-installation-output.png)

### Kali Hostname Output

![Kali hostname output](../screenshots/22-kali-hostname-output.png)

### Kali Short ip a Output

![Kali short ip a output](../screenshots/23-kali-ip-a-short-output.png)

## Active Directory Administration Tools

### Administrative Center corp.local

![Administrative Center corp.local](../screenshots/08-administrative-center-corp-local.png)

### Administrative Center User Management

![Administrative Center user management](../screenshots/24-administrative-center-user-management.png)

### ADUC Domain Object View

![ADUC domain object view](../screenshots/25-aduc-domain-object-view.png)

### ADUC Users Container View

![ADUC users container view](../screenshots/26-aduc-users-container-view.png)

## Phase 1 — Detection and Audit Policy Setup (Domain Controller)

### GPO: Audit Kerberos Service Ticket Operations

![GPO Audit Kerberos Service Ticket Operations](../screenshots/27-gpo-audit-kerberos-service-ticket-operations.png)

### GPO: Audit Kernel Object

![GPO Audit Kernel Object](../screenshots/28-gpo-audit-kernel-object.png)

### GPO: Audit Sensitive Privilege Use

![GPO Audit Sensitive Privilege Use](../screenshots/29-gpo-audit-sensitive-privilege-use.png)

### GPO: Audit Directory Service Changes

![GPO Audit Directory Service Changes](../screenshots/30-gpo-audit-directory-service-changes.png)

### GPO: Audit Account Lockout and Logon

![GPO Audit Account Lockout and Logon](../screenshots/31-gpo-audit-account-lockout-logon.png)

### GPO: Audit Process Creation

![GPO Audit Process Creation](../screenshots/32-gpo-audit-process-creation.png)

### GPO: Audit Kerberos Overview

![GPO Audit Kerberos Overview](../screenshots/33-gpo-audit-kerberos-overview.png)

### Group Policy Update Force

![gpupdate /force success](../screenshots/34-gpupdate-force-success.png)

### GPO: PowerShell Script Block Logging Enabled

![GPO PowerShell Script Block Logging enabled](../screenshots/35-gpo-powershell-script-block-logging-enabled.png)

### GPO: Audit Sensitive Privilege Use Review

![GPO Audit Sensitive Privilege Use review](../screenshots/36-gpo-audit-sensitive-privilege-use-review.png)

## Phase 2 — Mimikatz Attack (from Kali Linux)

### PowerShell: net localgroup administrators

![PowerShell net localgroup administrators](../screenshots/37-powershell-net-localgroup-admins.png)

### NetExec: Pwn3d Admin Access Confirmed

![NetExec Pwn3d admin access](../screenshots/38-netexec-pwn3d-admin-access.png)
