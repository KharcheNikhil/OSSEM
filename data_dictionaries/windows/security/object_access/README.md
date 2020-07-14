# Audit Object Access

## Description

Object Access policy settings and audit events allow you to track attempts to access specific objects or types of objects on a network or computer. To audit attempts to access a file, directory,registry key, or any other object, you must enable the appropriate object Aaccess auditing subcategory for success and/or failure events. For example, the file system subcategory needs to be enabled to audit file operations, and the Registry subcategory needs to be enabled to audit registry accesses.

Proving that these audit policies are in effect to an external auditor is more difficult. There is no easy way to verify that the proper SACLs are set on all inherited objects. To address this issue, see Global Object Access Auditing.[Microsoft Source](https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/advanced-security-audit-policy-settings#object-access)

## Subcategories

| Subcategory | Description | Event Volume |
|---------|-------|---------|
| [Audit Detailed File Share](https://github.com/Cyb3rWard0g/OSSEM/blob/master/data_dictionaries/windows/security/object_access/detailed_file_share/README.md) | Audit Detailed File Share allows you to audit attempts to access files and folders on a shared folder. | High on file servers. High on domain controllers because of SYSVOL network access required by Group Policy. Low on member servers and workstations. |
| [Audit File Share](https://github.com/Cyb3rWard0g/OSSEM/blob/master/data_dictionaries/windows/security/object_access/file_share/README.md) | Audit File Share allows you to audit events related to file shares: creation, deletion, modification, and access attempts. Also, it shows failed SMB SPN checks. | High on file servers. High on domain controllers because of SYSVOL network access required by Group Policy. Low on member servers and workstations. |
| [Audit File System](https://github.com/Cyb3rWard0g/OSSEM/blob/master/data_dictionaries/windows/security/object_access/file_system/README.md) | Audit File System determines whether the operating system generates audit events when users attempt to access file system objects. | Varies, depending on how file system SACLs are configured. |
| [Audit Filtering Platform Connection](https://github.com/Cyb3rWard0g/OSSEM/blob/master/data_dictionaries/windows/security/object_access/filtering_platform_connection/README.md) | Audit Filtering Platform Connection determines whether the operating system generates audit events when connections are allowed or blocked by the Windows Filtering Platform. | High |
| [Audit Filtering Platform Packet Drop](https://github.com/Cyb3rWard0g/OSSEM/blob/master/data_dictionaries/windows/security/object_access/filtering_platform_packet_drop/README.md) | Audit Filtering Platform Packet Drop determines whether the operating system generates audit events when packets are dropped by the Windows Filtering Platform. | High |
| [Audit Handle Manipulation](https://github.com/Cyb3rWard0g/OSSEM/blob/master/data_dictionaries/windows/security/object_access/handle_manipulation/README.md) | Audit Handle Manipulation enables generation of “4658: The handle to an object was closed” in Audit File System, Audit Kernel Object, Audit Registry, Audit Removable Storage and Audit SAM subcategories, and shows object’s handle duplication and close actions. | High |
| [Audit Kernel Object](https://github.com/Cyb3rWard0g/OSSEM/blob/master/data_dictionaries/windows/security/object_access/kernel_object/README.md) | Audit Kernel Object determines whether the operating system generates audit events when users attempt to access the system kernel, which includes mutexes and semaphores. | High |
| [Audit Other Object Access Events](https://github.com/Cyb3rWard0g/OSSEM/blob/master/data_dictionaries/windows/security/object_access/other_object_access/README.md) | Audit Other Object Access Events allows you to monitor operations with scheduled tasks, COM+ objects and indirect object access requests. | Low |
| [Audit Registry](https://github.com/Cyb3rWard0g/OSSEM/blob/master/data_dictionaries/windows/security/object_access/registry/README.md) | Audit Registry allows you to audit attempts to access registry objects. A security audit event is generated only for objects that have system access control lists (SACLs) specified, and only if the type of access requested, such as Read, Write, or Modify, and the account making the request match the settings in the SACL. | Low to Medium, depending on how registry SACLs are configured. |
| [Audit Removable Storage](https://github.com/Cyb3rWard0g/OSSEM/blob/master/data_dictionaries/windows/security/object_access/removable_storage/README.md) | Audit Removable Storage allows you to audit user attempts to access file system objects on a removable storage device. A security audit event is generated for all objects and all types of access requested, with no dependency on object’s SACL. |  |
| [Audit SAM](https://github.com/Cyb3rWard0g/OSSEM/blob/master/data_dictionaries/windows/security/object_access/sam/README.md) | Audit SAM, which enables you to audit events that are generated by attempts to access Security Account Manager (SAM) objects. | High on domain controllers. |
| [Audit Central Access Policy Staging](https://github.com/Cyb3rWard0g/OSSEM/blob/master/data_dictionaries/windows/security/object_access/central_access_policy/README.md) | Audit Central Access Policy Staging allows you to audit access requests where a permission granted or denied by a proposed policy differs from the current central access policy on an object. |   |