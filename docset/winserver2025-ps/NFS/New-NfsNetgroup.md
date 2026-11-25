---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FileServices.Powershell.NFS.dll-Help.xml
Module Name: NFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nfs/new-nfsnetgroup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NfsNetgroup
---

# New-NfsNetgroup

## SYNOPSIS
Creates a netgroup.

## SYNTAX

```
New-NfsNetgroup [-NetGroupName] <String> [[-AddMember] <String[]>] [[-LdapServer] <String>]
 [[-LdapNamingContext] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-NfsNetgroup** cmdlet creates a netgroup.
It can also add members to the new netgroup.
The netgroup provides access to shares that Network File System (NFS) server exports.

You can create a netgroup in Active Directory Domain Services (AD DS), on an Active Directory Lightweight Directory Services (AD LDS) server, or on Lightweight Directory Access Protocol (LDAP) servers.
If you do not specify a netgroup store, **New-NfsNetgroup** creates a netgroup in the netgroup store that is configured on the local computer.

The cmdlet creates the netgroup as a relative distinguished name in an LDAP naming context (directory partition).
For example, if the specified naming context is DN=netgroups,CN=Contoso,CN=com", the distinguished name of the netgroup Contoso-PrintServices is "DN= Contoso-PrintServices ,DN=netgroups,CN=Contoso,CN=com".

You can group NFS client computers logically into netgroups to easily manage mount permissions for all the computers that are in the group.
Because netgroups are a server-side setting, **New-NfsNetgroup** is not available on client operating systems.

## EXAMPLES

### Example 1: Create a netgroup and add a member
```
PS C:\> New-NfsNetgroup -NetGroupName "Contoso-PrintServices" -AddMember "Contoso-PS02" -LdapInstanceName "Contoso.com" -LdapNamingContext "CN=MappedIdentity,DC=Contoso,DC=com"
```

This command creates a netgroup that is named Contoso-PrintServices and adds one member that is named Contoso-PS02.

### Example 2: Create a netgroup and add multiple members
```
PS C:\> New-NfsNetgroup -NetGroupName "AppServers" -AddMember "Contoso-APPS-11","Contoso-APPS-12" -LdapServer "Contoso.com" -LdapNamingContext "CN=netgroup,DC=Contoso,DC=com"
```

This command creates a netgroup that is named AppServers and adds two members that are named Contoso-APPS-11 and Contoso-APPS-12.

## PARAMETERS

### -AddMember
Specifies the host names or IP addresses of the client computers to add to a netgroup.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: add

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -LdapNamingContext
Specifies the LDAP naming context of the new netgroup store.

```yaml
Type: String
Parameter Sets: (All)
Aliases: dn

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LdapServer
Specifies the LDAP server name of the new netgroup store.
The LDAP server name can be a domain name, AD LDS server name, or other LDAP server name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ldap

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetGroupName
Specifies the name of a new netgroup.

```yaml
Type: String
Parameter Sets: (All)
Aliases: name, ngname

Required: True
Position: 0
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

### Microsoft.FileServices.Powershell.Nfs.NetGroup

## NOTES

## RELATED LINKS

[Get-NfsNetgroup](./Get-NfsNetgroup.md)

[Remove-NfsNetgroup](./Remove-NfsNetgroup.md)

[Set-NfsNetgroup](./Set-NfsNetgroup.md)

