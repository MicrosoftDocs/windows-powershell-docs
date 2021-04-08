---
author: Kateyanne
external help file: NFS_Cmdlets.xml
manager: dansimp
Module Name: NFS
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/nfs/get-nfsmappedidentity?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NfsMappedIdentity

## SYNOPSIS
Gets an NFS mapped identity.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-NfsMappedIdentity [-MappingStore]
```

### UNNAMED_PARAMETER_SET_2
```
Get-NfsMappedIdentity [-AccountName <String>] [-GroupIdentifier <Int32>] [-UserIdentifier <Int32>]
 [-AccountType]
```

### UNNAMED_PARAMETER_SET_3
```
Get-NfsMappedIdentity [-LdapNamingContext <String>] [-Server <String>] [-MappingStore]
```

### UNNAMED_PARAMETER_SET_4
```
Get-NfsMappedIdentity [-MapFilesPath <String>] [-MappingStore]
```

## DESCRIPTION
The **Get-NfsMappedIdentity** cmdlet gets a Network File System (NFS) mapped identity.

A mapped identity associates a Windows user account or group account to a UNIX user account or group account.
A user ID (UID) or group ID (GID) identifies a UNIX account namespace.
These elements are associated with the corresponding elements of a Windows account namespace: a user name or a group name.
By using a mapped identity, a user who is logged on to a UNIX domain can access shared resources in a Windows domain without having to log on to the Windows domain.

For more information about NFS, see Network File Systemhttp://technet.microsoft.com/en-us/library/jj592688.
For more information about NFS account mapping, see NFS Account Mapping Guidehttp://technet.microsoft.com/en-us/library/hh509020(v=ws.10) and Identity Management for UNIXhttp://technet.microsoft.com/en-us/library/cc772571.

## EXAMPLES

### Example 1: Get a mapped identity for a user account by using a specified name
```
PS C:\> Get-NfsMappedIdentity -MappingStore "LDAP" -AccountType "User" -AccountName "RPatel"
```

This command gets all user account mapped identities from a configured AD LDS or RFC 2307-compliant LDAP store instance.
In this example, the command returns PrimaryGroup and SupplementaryGroups only when the configured mapping store is MapFiles.

### Example 2: Get all group account mapped identities from a specific store instance
```
PS C:\> Get-NfsMappedIdentity -MappingStore "LDAP" -AccountType "Group" -GroupName "Administrators"
```

This command gets all mapped identities in the Administrator group from a configured AD LDS or RFC 2307-compliant LDAP store instance.

### Example 3: Get a mapped identity for a group account by using a specified Id
```
PS C:\> Get-NfsMappedIdentity -MappingStore "LDAP" -AccountType "Group" -GroupIdentifier "GID99"
```

This command gets a mapped identity for the group account that has the GID 99, from a configured AD LDS or RFC 2307-compliant LDAP store instance.

### Example 4: Get all user account mapped identities from a specific mapping store
```
C:\PS> Get-NfsMappedIdentity -MappingStore "LDAP" -AccountType "User"
```

This command gets all user account mapped identities from a configured AD LDS or RFC 2307-compliant LDAP store instance.
PrimaryGroup and SupplementaryGroups are returned only when the configured mapping store is MapFiles.

### Example 5: Get all user account mapped identities from a mapping store that is specified in the NFS Server configuration settings
```
PS C:\>Get-NfsMappedIdentity -AccountType "User"
```

This command gets all user account mapped identities from a mapping store that is specified in the NFS server configuration settings.

## PARAMETERS

### -AccountName
Specifies the SAMAccountName of the Windows user account or group account of a mapped identity.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AccountType
Specifies the Windows account type of a mapped identity.
Supported values are User and Group.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 
Accepted values: User, Group

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GroupIdentifier
Specifies the group identifier of a user or group account.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LdapNamingContext
Specifies the Lightweight Directory Access Protocol (LDAP) naming context of the NFS identity mapping store.
You can use this parameter to search for mapped identities in the specified naming context.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: DefaultNamingContext
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MapFilesPath
Specifies the path of the passwd and group map files from which the **Get-NfsMappedIdentity** cmdlet gets a mapped identity.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: %SystemRoot\System32\Drivers\etc\
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MappingStore
Specifies the type of identity mapping store from which the **Get-NfsMappedIdentity** cmdlet gets a mapped identity.
When this parameter is not specified, the cmdlet gets the store configuration settings from the NFS server configuration where this command is run configuration where this command is run.
Valid values are: **AD**, **LDAP**, and **MapFiles**.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 
Accepted values: Ad, Ldap, Mapfiles

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 
Accepted values: Ad, Ldap, Mapfiles

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Server
Specifies the LDAP instance name of the store that NFS server uses.
This can be an Active Directory domain name, Active Directory Lightweight Directory Services (AD LDS) server name, or LDAP server name.
When this parameter is not specified, the cmdlet tries to connect to either the LDAP store on the local computer at port 389 when MappingStore is LDAP, or the Active Directory domain of the computer when MappingStore is Active Directory.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: Localhost:389
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserIdentifier
Specifies the UID of the user account.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### System.FileServices.Management.Nfs.UserMappedIdentity, System.FileServices.Management.Nfs.GroupMappedIdentity

## NOTES

## RELATED LINKS

[RFC-2307](http://www.rfc-editor.org/rfc/rfc2307.txt)

[Get-NfsMappedIdentity](./Get-NfsMappedIdentity.md)

[New-NfsMappedIdentity](./New-NfsMappedIdentity.md)

[Remove-NfsMappedIdentity](./Remove-NfsMappedIdentity.md)

[Resolve-NfsMappedIdentity](./Resolve-NfsMappedIdentity.md)

[Set-NfsMappedIdentity](./Set-NfsMappedIdentity.md)

[Test-NfsMappedIdentity](./Test-NfsMappedIdentity.md)

[Get-NfsMappingStore](./Get-NfsMappingStore.md)

[Install-NfsMappingStore](./Install-NfsMappingStore.md)

[Set-NfsMappingStore](./Set-NfsMappingStore.md)

[Test-NfsMappingStore](./Test-NfsMappingStore.md)

