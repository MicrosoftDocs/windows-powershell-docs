---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FileServices.Powershell.NFS.dll-Help.xml
Module Name: NFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nfs/set-nfsmappedidentity?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NfsMappedIdentity
---

# Set-NfsMappedIdentity

## SYNOPSIS
Modifies a mapped identity.

## SYNTAX

### User (Default)
```
Set-NfsMappedIdentity [-MappingStore <MappingStoreType>] [-Server <String>] [-LdapNamingContext <String>]
 -UserName <String> [-UserIdentifier <Int32>] [-GroupIdentifier <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Group
```
Set-NfsMappedIdentity [-MappingStore <MappingStoreType>] [-Server <String>] [-LdapNamingContext <String>]
 -GroupName <String> -GroupIdentifier <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NfsMappedIdentity** cmdlet modifies a mapped identity that is stored in the Network File System (NFS) server mapping store.
The cmdlet also updates the group membership of the Windows user account to match its assigned group identifier (GID).

## EXAMPLES

### Example 1: Modify a mapped identity that is stored in an AD LDS instance
```
PS C:\> Set-NfsMappedIdentity -MappingStore "LDAP" -GroupName "Administrators" -GroupIdentifier 600
```

This command modifies a mapped identity that is stored in a configured AD LDS instance and that corresponds to the Windows group account Administrators.
The command resets the associated group identifier to 600.

### Example 2: Modify a mapped identity that is stored in an Active Directory domain
```
PS C:\> Set-NfsMappedIdentity -Store "AD" -Server "Contoso"-UserName "JCool" -UserIdentifier 501 -GroupIdentifier 600
```

This command modifies a mapped identity that is stored in a specified Active Directory domain and that corresponds to the user account JCool.
The command sets the user identifier to 501 and the group identifier to 600, and it updates the group membership of the user account JCool to make it a member of a group account that has GID 600.

### Example 3: Modify a mapped identity that is stored in a configured LDAP store
```
PS C:\> Set-NfsMappedIdentity -Store "LDAP" -UserName "JCool" -UserIdentifier 501 -GroupIdentifier 600 -Server "MyLdapServer:389" -LdapNamingContext "CN=NFS,DC=NFS"
```

This command modifies a mapped identity that is stored in the LDAP store on a specified server that is named MyLdapServer and that corresponds to the user account Contoso\JCool.
It sets the user identifier to 501 and the group identifier to 600.
The command also adds the user account JCool to GID 600.

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
Parameter Sets: User
Aliases: GroupId, gid

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: Int32
Parameter Sets: Group
Aliases: GroupId, gid

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GroupName
Specifies the SAMAccountName of a Windows group account.

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
Specifies the Lightweight Directory Access Protocol (LDAP) naming context (directory partition) of an NFS identity mapping store.
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
Specifies the type of identity mapping store in which the **Set-NfsMappedIdentity** cmdlet updates a mapped identity.
When this parameter is not specified, the **Set-NfsMappedIdentity** cmdlet gets the store configuration settings from the NFS server.
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
Specifies the LDAP server name of a store that NFS server uses.
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

### -UserIdentifier
Specifies a UID to assign to a user account that the *UserName* parameter specifies.

```yaml
Type: Int32
Parameter Sets: User
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

[Remove-NfsMappedIdentity](./Remove-NfsMappedIdentity.md)

[Resolve-NfsMappedIdentity](./Resolve-NfsMappedIdentity.md)

[Set-NfsMappingStore](./Set-NfsMappingStore.md)

[Test-NfsMappedIdentity](./Test-NfsMappedIdentity.md)

[Test-NfsMappingStore](./Test-NfsMappingStore.md)

