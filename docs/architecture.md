# Architecture

This lab uses three virtual machines connected through a private VirtualBox internal network. A second NAT adapter provides internet access for updates and package installation.

## High-Level Network Topology

```mermaid
graph LR
    Internet[Internet] --> NAT[NAT Adapter]
    NAT --> DC[Windows Server 2022 Domain Controller]
    DC --> AD[AD DS and DNS]
    DC --> Internal[Internal Enterprise Network]
    Internal --> WIN11[Windows 11 Workstation]
    Internal --> KALI[Kali Linux Management VM]
    WIN11 --> DC
    KALI --> DC
```

## Enterprise Service Flow

```mermaid
graph LR
    WIN11[Windows 11 Workstation] --> DNS[DNS Query for corp.local]
    DNS --> DC[Windows Server 2022 Domain Controller]
    WIN11 --> AUTH[Domain Authentication]
    AUTH --> KERB[Kerberos]
    KERB --> AD[Active Directory Domain Services]
    AD --> USER[Domain User Access]
```

## VirtualBox Adapter Layout

```mermaid
graph LR
    DC[Windows Server 2022] --> DCINT[Adapter 1 Internal Network]
    DC --> DCNAT[Adapter 2 NAT]
    WIN11[Windows 11] --> WINT[Adapter 1 Internal Network]
    WIN11 --> WNAT[Adapter 2 NAT]
    KALI[Kali Linux] --> KINT[Adapter 1 Internal Network]
    KALI --> KNAT[Adapter 2 NAT]
    DCINT --> LABNET[Internal Enterprise Network]
    WINT --> LABNET
    KINT --> LABNET
    DCNAT --> INTERNET[Internet Access]
    WNAT --> INTERNET
    KNAT --> INTERNET
```

## Domain Deployment Flow

```mermaid
graph LR
    A[Install Windows Server 2022] --> B[Configure Server Manager]
    B --> C[Install AD DS Role]
    B --> D[Install DNS Role]
    C --> E[Promote Server to Domain Controller]
    D --> E
    E --> F[Create New Forest corp.local]
    F --> G[Validate Domain with Get-ADDomain]
    G --> H[Manage Domain with ADUC and ADAC]
```

## Lab Systems

| System | Network Role | Infrastructure Function |
| --- | --- | --- |
| Windows Server 2022 | Core server | Domain controller, AD DS, DNS |
| Windows 11 Pro | Domain workstation | Enterprise client endpoint |
| Kali Linux | Linux management VM | Network validation and administration |

## Network Purpose

| Network | Purpose |
| --- | --- |
| Internal Network | Isolated enterprise communication for AD DS, DNS, Kerberos, SMB, and LDAP |
| NAT | Internet access for updates, browser access, and package installation |
