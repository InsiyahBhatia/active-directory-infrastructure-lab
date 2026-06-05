# Phase 3: Domain Controller Deployment

Windows Server 2022 was installed and prepared to become the central authentication and directory services host.

## Initial Server Configuration

After installing Windows Server 2022, the server was prepared for domain services.

Configuration steps:

1. Install Windows Server 2022 from the ISO.
2. Set the local Administrator password.
3. Sign in with the Administrator account.
4. Open Server Manager.
5. Confirm the server hostname.
6. Confirm both network adapters are available.
7. Verify internet access through the NAT adapter.
8. Verify internal network connectivity through the internal adapter.

Recommended server preparation:

- Rename the server to a clear domain controller name, such as `DC01`.
- Configure the internal adapter for the enterprise network.
- Ensure the NAT adapter remains available for updates.
- Install Windows updates if required.
- Confirm Server Manager opens without errors.

## Installing AD DS and DNS

AD DS and DNS were installed through Server Manager:

```text
Manage -> Add Roles and Features
```

Role installation steps:

1. Select `Role-based or feature-based installation`.
2. Select the local Windows Server 2022 machine.
3. Choose `Active Directory Domain Services`.
4. Accept the required management tools.
5. Choose `DNS Server`.
6. Accept the required DNS management tools.
7. Continue through the wizard.
8. Select `Install`.
9. Wait for the role installation to finish.

Installed roles:

```text
Active Directory Domain Services
DNS Server
```

At this stage, the server has the required roles installed, but it is not yet a domain controller. The next step is promotion.
