---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FileServices.Powershell.NFS.dll-Help.xml
Module Name: NFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nfs/remove-nfsmappedidentity?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-NfsMappedIdentity
---

# Remove-NfsMappedIdentity

## SYNOPSIS
Removes a mapping between a UNIX account and a Windows account.

## SYNTAX

### User (Default)
```
Remove-NfsMappedIdentity [-MappingStore <MappingStoreType>] [-Server <String>] [-LdapNamingContext <String>]
 -UserName <String> [-UserIdentifier <Int32>] [-GroupIdentifier <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Group
```
Remove-NfsMappedIdentity [-MappingStore <MappingStoreType>] [-Server <String>] [-LdapNamingContext <String>]
 -GroupName <String> [-GroupIdentifier <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Default
```
Remove-NfsMappedIdentity [-MappingStore <MappingStoreType>] [-Server <String>] [-LdapNamingContext <String>]
 [-UserIdentifier <Int32>] [-GroupIdentifier <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-NfsMappedIdentity** cmdlet removes a mapped identity from a Network File System (NFS) server mapping store.

A mapped identity associates a Windows user account or group account to a UNIX user account or group account.
A user ID (UID) or group ID (GID) identifies a UNIX account namespace.
These elements are associated with the corresponding elements of a Windows account namespace: a user name or a group name.
By using a mapped identity, a user who is logged on to a UNIX domain can access shared resources in a Windows domain without having to log on to the Windows domain.

For more information about NFS, see [Network File System Overview](https://technet.microsoft.com/en-us/library/jj592688).
For more information about NFS account mapping, see [NFS Account Mapping Guide](https://technet.microsoft.com/en-us/library/hh509020(v=ws.10)) and [Identity Management for UNIX](https://technet.microsoft.com/en-us/library/cc772571).

## EXAMPLES

### Example 1: Remove identity mapping for a user
```
PS C:\> Remove-NfsMappedIdentity -MappingStore "LDAP" -UserName "LSPolly"
```

This command removes a mapped identity that is stored in the configured AD LDS instance, on a server where this command is run, for the user account LSPolly.

### Example 2: Remove an identity mapping for a group
```
PS C:\> Remove-NfsMappedIdentity -MappingStore "AD" -GroupIdentifier 22
```

This command removes a mapped identity that is stored in a configured AD DS map store and that corresponds to the group account that has the group identifier 22.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupIdentifier
Specifies the group identifier of a mapped identity.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: GroupId, gid

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GroupName
Specifies the SAMAccountName of the group account.

```yaml
Type: String
Parameter Sets: Group
Aliases: group

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LdapNamingContext
Specifies the Lightweight Directory Access Protocol (LDAP) naming context of an NFS identity mapping store.
You can use this parameter to search for mapped identities in the specified naming context.

```yaml
Type: String
Parameter Sets: (All)
Aliases: dn

Required: False
Position: Named
Default value: DefaultNamingContext
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MappingStore
Specifies the type of identity mapping store from which the **Remove-NfsMappedIdentity** cmdlet removes a mapped identity.
When this parameter is not specified, the **Remove-NfsMappedIdentity** cmdlet gets the store configuration settings from the NFS server.
Valid values are AD and LDAP.

```yaml
Type: MappingStoreType
Parameter Sets: (All)
Aliases: store
Accepted values: Ad, Ldap, Mapfiles

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Server
Specifies the LDAP server instance of a store that NFS server uses.
This can be a domain name, Active Directory Lightweight Directory Services (AD LDS) server name, or LDAP server name.
When this parameter is not specified, the **Remove-NfsMappedIdentity** cmdlet tries to connect to either the LDAP store on the local computer at port 389 when **MappingStore** is LDAP, or the Active Directory Domain Services (AD DS) domain of the computer when **MappingStore** is Active Directory.

```yaml
Type: String
Parameter Sets: (All)
Aliases: LdapServer, ADDomainName

Required: False
Position: Named
Default value: Localhost:389
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserIdentifier
Specifies the user identifier of a user account.

```yaml
Type: Int32
Parameter Sets: User, Default
Aliases: UserId, uid

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserName
Specifies the SAMAccountName of a user account.

```yaml
Type: String
Parameter Sets: User
Aliases: user

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Nothing

## NOTES

## RELATED LINKS

[Get-NfsMappedIdentity](./Get-NfsMappedIdentity.md)

[Get-NfsMappingStore](./Get-NfsMappingStore.md)

[Install-NfsMappingStore](./Install-NfsMappingStore.md)

[New-NfsMappedIdentity](./New-NfsMappedIdentity.md)

[Resolve-NfsMappedIdentity](./Resolve-NfsMappedIdentity.md)

[Set-NfsMappedIdentity](./Set-NfsMappedIdentity.md)

[Set-NfsMappingStore](./Set-NfsMappingStore.md)

[Test-NfsMappedIdentity](./Test-NfsMappedIdentity.md)

[Test-NfsMappingStore](./Test-NfsMappingStore.md)

