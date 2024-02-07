---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FileServices.Powershell.NFS.dll-Help.xml
Module Name: NFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nfs/new-nfsmappedidentity?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NfsMappedIdentity
---

# New-NfsMappedIdentity

## SYNOPSIS
Creates a new NFS mapped identity.

## SYNTAX

### User (Default)
```
New-NfsMappedIdentity [-MappingStore <MappingStoreType>] [-Server <String>] [-LdapNamingContext <String>]
 -UserName <String> [-Password <SecureString>] -UserIdentifier <Int32> -GroupIdentifier <Int32>
 [-PrimaryGroup <String>] [-SupplementaryGroups <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Group
```
New-NfsMappedIdentity [-MappingStore <MappingStoreType>] [-Server <String>] [-LdapNamingContext <String>]
 -GroupName <String> [-Password <SecureString>] -GroupIdentifier <Int32> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-NfsMappedIdentity** cmdlet creates a new Network File System (NFS) mapped identity between a UNIX user account or group account and a Windows user account or group account.
If a specified user account or group account does not exist, the **New-NfsMappedIdentity** cmdlet can create the account, set its user ID (UID) and group ID (GID) attributes, and update user membership in the group.

A mapped identity associates a Windows user account or group account to a UNIX user account or group account.
A UID or GID identifies a UNIX account namespace.
These elements are associated with the corresponding elements of a Windows account namespace: a user name or a group name.
By using a mapped identity, a user who is logged on to a UNIX domain can access shared resources in a Windows domain without having to log on to the Windows domain.

For more information about NFS, see [Network File System Overview](https://technet.microsoft.com/en-us/library/jj592688).
For more information about NFS account mapping, see [NFS Account Mapping Guide](https://technet.microsoft.com/en-us/library/hh509020(v=ws.10)) and [Identity Management for UNIX](https://technet.microsoft.com/en-us/library/cc772571).

## EXAMPLES

### Example 1: Create a mapped identify for a UNIX user account and a Windows user account
```
PS C:\> New-NfsMappedIdentity -MappingStore "AD" -Server "Contoso" -UserName "JBrown" -UserIdentifier 500 -GroupIdentifier 41
```

This command creates a mapped identity for a UNIX user that has a UID of 500, and maps it to the Windows account name Contoso\JBrown in a Windows group that has the group identifier of 41.
The command stores the mapped identity in the configured Active Directory domain of the local computer.
If the user account does not already exist, the command creates it.

### Example 2: Create a mapped identity for a UNIX group account and a Windows group account
```
PS C:\> New-NfsMappedIdentity -MappingStore "Ldap" -GroupName "Operators" -GroupIdentifier 501 -Server "LdapServer01:389" -NfsServer "NFSServer-012"
```

This command creates a mapped identity for a UNIX group that has a group identifier of 501 and maps it to the Windows group account that is named Operators.
The mapped identity is stored in the configured LDAP store on the computer that is named LdapServer01, that the NFS server NFSServer-012 uses.
The command also creates a local group account named Operators on the NFS server NFSServer-012 if it does not already exist.

### Example 3: Create an identity mapping and create the user account and group account if they do not exist
```
PS C:\> New-NfsMappedIdentity -MappingStore "AD" -Server "Contoso" -UserName "JCool" -UserIdentifier 500 -GroupIdentifier 501 -PrimaryGroup "Operators"
```

This command creates a mapped identity for a UNIX user whose UID is 500 and maps it to the Windows account named Contoso\JCool.
The mapped identity is stored in the Active Directory domain named Contoso.
If the user account Contoso\JCool does not exist, the command creates the user account.
If the group account Operators does not exist, the command creates the group, assigns GID 501 to the group, and adds the user account Contoso\JCool to the group.

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
Specifies a group identifier of a user or group account.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: GroupId, gid

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GroupName
Specifies a SAMAcccount name of a group account.

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
Specifies the Lightweight Directory Access Protocol (LDAP) naming context (directory partition) of the identity mapping store that NFS uses.
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
Specifies the type of identity mapping store in which the **New-NfsMappedIdentity** cmdlet creates a mapped identity.
When the MappingStore  is not specified, the **New-NfsMappedIdentity** cmdlet gets the store configuration settings from an NFS server.
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

### -Password
Specifies a password for a user account that the **New-NfsMappedIdentity** cmdlet creates.
If no password is specified, the cmdlet disables the new user account until a password is set.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PrimaryGroup
Specifies the name of the group account that the cmdlet creates if no existing group account has the specified group identifier.
In this case, the *GroupIdentifier* parameter assigns a GID to the group account.

```yaml
Type: String
Parameter Sets: User
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Server
Specifies the LDAP instance name of the store that an NFS server uses.
This can be a domain name, Active Directory Lightweight Directory Services (AD LDS) server name, or LDAP server name.
When this parameter is not specified, the cmdlet tries to connect to either the LDAP store on the local computer at port 389 when *MappingStore* is LDAP, or the Active Directory domain of the computer when *MappingStore* is Active Directory.

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

### -SupplementaryGroups
Specifies a comma-separated list of group names to which the cmdlet adds a user account that the *UserName* parameter specifies.

```yaml
Type: String
Parameter Sets: User
Aliases: sg

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserIdentifier
Specifies the user identifier that the cmdlet assigns to the user account that the *UserName* parameter specifies.

```yaml
Type: Int32
Parameter Sets: User
Aliases: UserId, uid

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserName
Specifies a SAMAcccount name of a user account.

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

[Remove-NfsMappedIdentity](./Remove-NfsMappedIdentity.md)

[Resolve-NfsMappedIdentity](./Resolve-NfsMappedIdentity.md)

[Set-NfsMappedIdentity](./Set-NfsMappedIdentity.md)

[Set-NfsMappingStore](./Set-NfsMappingStore.md)

[Test-NfsMappedIdentity](./Test-NfsMappedIdentity.md)

[Test-NfsMappingStore](./Test-NfsMappingStore.md)

