# Phase 8: Kali Linux Management VM Deployment

Kali Linux was installed as a Linux administration and testing system. In this infrastructure-focused repository, Kali is used for system administration and network validation rather than attack activity.

## Kali Setup

Configuration steps:

1. Create the Kali VM in VirtualBox.
2. Assign 4 GB RAM, 2 CPUs, and a 40 GB virtual disk.
3. Attach the Kali Linux ISO.
4. Install Kali Linux.
5. Create a local user account.
6. Configure Adapter 1 as the same internal network used by the Windows systems.
7. Configure Adapter 2 as NAT.
8. Boot Kali and verify both interfaces.

## Validation Commands

Basic validation:

```bash
hostname
ip a
```

Additional validation:

```bash
ip route
cat /etc/resolv.conf
ping <domain-controller-ip>
nslookup corp.local
```

Validated:

- Kali hostname
- Network interfaces
- Internal network connectivity
- NAT-based internet access

The internal interface should allow Kali to communicate with the Windows Server 2022 domain controller. The NAT interface should allow Kali to install packages and reach external repositories.
