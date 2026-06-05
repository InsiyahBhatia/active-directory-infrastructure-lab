# Phase 6: Active Directory Administration

Active Directory administration was validated using both classic and modern Microsoft management tools.

## Active Directory Users and Computers

Navigation path:

```text
Tools -> Active Directory Users and Computers
```

ADUC validation steps:

1. Open Server Manager.
2. Select `Tools`.
3. Open `Active Directory Users and Computers`.
4. Expand the `corp.local` domain.
5. Review the default containers and organizational structure.

Verified domain structure:

- `corp.local`
- Users container
- Computers container
- Domain Controllers container
- Built-in groups

## Active Directory Administrative Center

Navigation path:

```text
Tools -> Active Directory Administrative Center
```

ADAC validation steps:

1. Open Server Manager.
2. Select `Tools`.
3. Open `Active Directory Administrative Center`.
4. Confirm the `corp.local` domain is visible.
5. Review domain objects and administrative options.

Administrative focus:

- User management
- Group management
- Domain object review
- Fine-grained AD administration

The AD management tools confirm that the domain was created successfully and that the server can manage users, computers, groups, and domain-level objects.
