# Architecture

This lab uses three virtual machines connected through a private VirtualBox internal network. A second NAT adapter provides internet access for updates and package installation.

## High-Level Network Topology

```mermaid
graph LR
    Internet[Internet] --> NAT[NAT Adapter]
    NAT --> DC[Windows Server 2022 Domain Controller]
    DC --> DOMAIN[corp.local]
    DOMAIN --> LAN[Internal Enterprise Network]
    LAN --> WIN11[Windows 11 Workstation]
    LAN --> KALI[Kali Linux Management VM]
```

## Domain Deployment Flow

```mermaid
graph LR
    A[Install Windows Server 2022] --> B[Install AD DS and DNS]
    B --> C[Promote Domain Controller]
    C --> D[Create corp.local]
    D --> E[Deploy Windows 11]
    E --> F[Configure Kali Linux]
    F --> G[Validate Infrastructure]
```

## Network Purpose

| Network | Purpose |
| --- | --- |
| Internal Network | Isolated enterprise communication for AD DS, DNS, Kerberos, SMB, and LDAP |
| NAT | Internet access for updates, browser access, and package installation |
