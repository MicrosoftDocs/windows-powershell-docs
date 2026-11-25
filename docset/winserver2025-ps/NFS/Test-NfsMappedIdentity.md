---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FileServices.Powershell.NFS.dll-Help.xml
Module Name: NFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nfs/test-nfsmappedidentity?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-NfsMappedIdentity
---

# Test-NfsMappedIdentity

## SYNOPSIS
Verifies that a mapped identity is correctly configured.

## SYNTAX

### DefaultSettings (Default)
```
Test-NfsMappedIdentity [-MappingStore <MappingStoreType>] [-UserIdentifier <Int32>] [-GroupIdentifier <Int32>]
 [-AccountName <String>] [-AccountType <AccountType>] [-SupplementaryGroups <String>] [<CommonParameters>]
```

### AdAdlds
```
Test-NfsMappedIdentity -MappingStore <MappingStoreType> [-Server <String>] [-LdapNamingContext <String>]
 [-UserIdentifier <Int32>] [-GroupIdentifier <Int32>] [-AccountName <String>] [-AccountType <AccountType>]
 [-SupplementaryGroups <String>] [<CommonParameters>]
```

### MapFiles
```
Test-NfsMappedIdentity -MappingStore <MappingStoreType> [-MapFilesPath <String>] [-UserIdentifier <Int32>]
 [-GroupIdentifier <Int32>] [-AccountName <String>] [-AccountType <AccountType>]
 [-SupplementaryGroups <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Test-NfsMappedIdentity** cmdlet verifies a mapped identity and confirms that it is configured correctly.
The **Test-NfsMappedIdentity** cmdlet checks a mapped identity for duplicate user identifiers (UIDs) or group identifiers (GIDs).
It also validates that the user accounts are members of the correct group account according to the GIDs that are assigned to them.

## EXAMPLES

### Example 1: Verify a mapped identity that is stored in a AD LDS instance
```
PS C:\> Test-NfsMappedIdentity -MappingStore "LDAP" -AccountName "JCool" -AccountType "User" -Verbose
VERBOSE: No errors found.
```

This command verifies a mapped identity that is stored in a AD LDS instance on a server where this command is run..

## PARAMETERS

### -AccountName
Specifies the SAMAccountName of the Windows user account or group account of a mapped identity.

```yaml
Type: String
Parameter Sets: (All)
Aliases: aname, an

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AccountType
Specifies the Windows account type of a mapped identity.
Valid values are: User and Group.

```yaml
Type: AccountType
Parameter Sets: (All)
Aliases: atype, at
Accepted values: User, Group

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -LdapNamingContext
Specifies the Lightweight Directory Access Protocol (LDAP) naming context of an NFS identity mapping store.
You can use this parameter to search for mapped identities in a specified naming context.

```yaml
Type: String
Parameter Sets: AdAdlds
Aliases: dn

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MapFilesPath
Specifies the path of the passwd and group map files from which the **Test-NfsMappedIdentity** cmdlet obtains a mapped identity.

```yaml
Type: String
Parameter Sets: MapFiles
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MappingStore
Specifies the type of identity mapping store from which the **Test-NfsMappedIdentity** cmdlet gets a mapped identity.
When this parameter is not specified, the **Test-NfsMappedIdentity** cmdlet obtains the store configuration settings from the NFS server configuration.
Valid values are: AD, LDAP, and MapFiles.

```yaml
Type: MappingStoreType
Parameter Sets: DefaultSettings
Aliases: store
Accepted values: Ad, Ldap, Mapfiles

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: MappingStoreType
Parameter Sets: AdAdlds, MapFiles
Aliases: store
Accepted values: Ad, Ldap, Mapfiles

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Server
Specifies the LDAP server name of the store that NFS server uses.
This can be a domain name, Active Directory Lightweight Directory Services (AD LDS) server name, or LDAP server name.
When this parameter is not specified, the **Test-NfsMappedIdentity** cmdlet tries to connect to either the LDAP store on the local computer at port 389 when *MappingStore* is LDAP, or the Active Directory domain of the computer when *MappingStore* is Active Directory.

```yaml
Type: String
Parameter Sets: AdAdlds
Aliases: LdapServer, ADDomainName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SupplementaryGroups
Specifies a comma-separated list of group names to verify the group membership of an account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: sg

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserIdentifier
Specifies the user identifier of a UNIX user account from which the **Test-NfsMappedIdentity** cmdlet obtains a mapped identity.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: UserId, uid

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-NfsMappedIdentity](./Get-NfsMappedIdentity.md)

[Get-NfsMappingStore](./Get-NfsMappingStore.md)

[Install-NfsMappingStore](./Install-NfsMappingStore.md)

[New-NfsMappedIdentity](./New-NfsMappedIdentity.md)

[Remove-NfsMappedIdentity](./Remove-NfsMappedIdentity.md)

[Resolve-NfsMappedIdentity](./Resolve-NfsMappedIdentity.md)

[Set-NfsMappedIdentity](./Set-NfsMappedIdentity.md)

[Set-NfsMappingStore](./Set-NfsMappingStore.md)

[Test-NfsMappingStore](./Test-NfsMappingStore.md)

