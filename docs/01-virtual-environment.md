# Phase 1: Virtual Environment Design

The lab was built in VirtualBox using three separate virtual machines. Each VM was created with a dedicated virtual disk, assigned CPU and memory resources, and installed from its operating system ISO.

## Virtual Machines

| VM | Operating System | Purpose | Resources |
| --- | --- | --- | --- |
| Domain Controller | Windows Server 2022 | Core infrastructure server | 4 GB RAM, 2 CPUs, 60 GB storage |
| Workstation | Windows 11 Pro | Enterprise endpoint | 4 GB RAM, 2 CPUs, 60 GB storage |
| Management System | Kali Linux | Linux administration VM | 4 GB RAM, 2 CPUs, 40 GB storage |

## Windows Server 2022 VM Configuration

Windows Server 2022 was configured as the core infrastructure server. During VM creation, the server was assigned 4 GB RAM, 2 virtual CPUs, and a 60 GB virtual disk.

Configuration steps:

1. Open VirtualBox and select `New`.
2. Name the VM for the domain controller, such as `DC01`.
3. Select Windows Server as the operating system type.
4. Assign 4 GB RAM.
5. Assign 2 virtual CPUs.
6. Create a 60 GB virtual hard disk.
7. Attach the Windows Server 2022 ISO.
8. Boot the VM and complete the operating system installation.
9. Configure the local Administrator password.
10. Sign in and confirm Server Manager opens successfully.

## Windows 11 VM Configuration

Windows 11 Pro was configured as the enterprise workstation. This system represents a normal employee endpoint that can be connected to the internal enterprise network and later joined to Active Directory.

Configuration steps:

1. Open VirtualBox and select `New`.
2. Name the VM for the workstation, such as `WIN11`.
3. Select Windows 11 as the operating system type.
4. Assign 4 GB RAM.
5. Assign 2 virtual CPUs.
6. Create a 60 GB virtual hard disk.
7. Attach the Windows 11 ISO.
8. Boot the VM and complete the Windows installation.
9. Complete initial setup.
10. Confirm the system boots normally.

## Kali Linux VM Configuration

Kali Linux was configured as a Linux-based management and testing VM. In this repository, Kali is used for administration and validation rather than attack activity.

Configuration steps:

1. Open VirtualBox and select `New`.
2. Name the VM for Kali Linux.
3. Select Linux as the operating system type.
4. Assign 4 GB RAM.
5. Assign 2 virtual CPUs.
6. Create a 40 GB virtual hard disk.
7. Attach the Kali Linux ISO.
8. Boot the VM and complete installation.
9. Create a local user account.
10. Confirm Kali boots to the desktop or terminal.

## Baseline Snapshot

After each operating system was installed, a clean baseline snapshot should be created. This allows the lab to be restored if later configuration changes fail.

Recommended snapshot points:

- Fresh Windows Server 2022 installation
- Fresh Windows 11 installation
- Fresh Kali Linux installation
- Domain controller after successful AD DS promotion
