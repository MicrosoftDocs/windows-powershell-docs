---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FileServices.Powershell.NFS.dll-Help.xml
Module Name: NFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nfs/set-nfsnetgroup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NfsNetgroup
---

# Set-NfsNetgroup

## SYNOPSIS
Modifies a netgroup.

## SYNTAX

```
Set-NfsNetgroup [-NetGroupName] <String> [[-AddMember] <String[]>] [[-RemoveMember] <String[]>]
 [[-LdapServer] <String>] [[-LdapNamingContext] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NfsNetgroup** cmdlet adds or removes netgroup members.
You can specify a netgroup member by its host name or IP address.

You can modify netgroups that are stored in Active Directory Domain Services (AD DS) or Active Directory Lightweight Directory Services (AD LDS) only.
To modify a netgroup that is stored in Network Information Service (NIS), use the corresponding NIS administration tool.
For more information about how to manage an NIS server, see [Server for NIS Administration](https://technet.microsoft.com/en-us/library/cc753089).

## EXAMPLES

### Example 1: Add a member to a netgroup
```
PS C:\> Set-NfsNetgroup -LdapServer "Contoso.com" -NetGroupName "AppServers" -AddMember "APPServer-08"
NetgroupName          : AppServers
NetgroupNamingContext : CN=mappedidentity,DC=Contoso,DC=com
NetgroupMembers       : {appserver-08, appserver-07}
```

This command adds a member that is named APPServer-08 to a netgroup that is named AppServers, in a network store that is named Contoso.com.

## PARAMETERS

### -AddMember
Specifies an array of host names or IP addresses of client computers to add to a netgroup.

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
Specifies the Lightweight Directory Access Protocol (LDAP) naming context of a netgroup store.

```yaml
Type: String
Parameter Sets: (All)
Aliases: dn

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LdapServer
Specifies an LDAP server name of a netgroup store.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ldap

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetGroupName
Specifies the name of a netgroup.
This parameter is mandatory.

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

### -RemoveMember
Specifies an array of host names or IP addresses of client computers to remove from a netgroup.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: remove

Required: False
Position: 2
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

[New-NfsNetgroup](./New-NfsNetgroup.md)

[Remove-NfsNetgroup](./Remove-NfsNetgroup.md)

