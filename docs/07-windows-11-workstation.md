# Phase 7: Windows 11 Workstation Deployment

Windows 11 Pro was installed and configured as an enterprise workstation. This VM represents a domain client system on the internal network.

## Workstation Setup

Configuration steps:

1. Create the Windows 11 VM in VirtualBox.
2. Assign 4 GB RAM, 2 CPUs, and a 60 GB virtual disk.
3. Attach the Windows 11 ISO.
4. Install Windows 11 Pro.
5. Complete the initial setup.
6. Configure the network adapters in VirtualBox.
7. Boot into Windows 11 and verify network interfaces.

## Network Validation

Network validation command:

```cmd
ipconfig
```

Expected validation points:

- One adapter connected to the internal enterprise network.
- One adapter connected to NAT.
- Internal adapter can communicate with the domain controller.
- NAT adapter can reach the internet.

Useful workstation validation commands:

```cmd
ipconfig
ipconfig /all
nslookup corp.local
```

## Domain Join Configuration

For domain integration, the Windows 11 system should use the domain controller as DNS on the internal adapter. This allows Windows to locate `corp.local` and discover domain services.

Domain join path:

```text
Settings -> System -> About -> Domain or workgroup -> Join a domain
```

Domain join value:

```text
corp.local
```

Domain join process:

1. Confirm the Windows 11 internal adapter is on the same internal network as the domain controller.
2. Configure the internal adapter DNS server to point to the domain controller.
3. Open the domain join settings.
4. Enter `corp.local`.
5. Provide domain administrator credentials when prompted.
6. Restart the workstation.
7. Sign in with a domain account after reboot.

Validated:

- Internal network adapter
- NAT adapter
- Domain network connectivity
- Workstation readiness for enterprise integration
