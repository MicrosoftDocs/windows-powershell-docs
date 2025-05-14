---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/new-rdsessioncollection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-RDSessionCollection
---

# New-RDSessionCollection

## SYNOPSIS
Creates a session collection of RD Session Host servers.

## SYNTAX

### PersonalSessionCollection
```
New-RDSessionCollection [-CollectionName] <String> [-CollectionDescription <String>] -SessionHost <String[]>
 [-ConnectionBroker <String>] [-PersonalUnmanaged] [-AutoAssignUser] [-GrantAdministrativePrivilege]
 [<CommonParameters>]
```

### PooledSessionCollection
```
New-RDSessionCollection [-CollectionName] <String> [-CollectionDescription <String>] -SessionHost <String[]>
 [-ConnectionBroker <String>] [-PooledUnmanaged] [<CommonParameters>]
```

## DESCRIPTION
The **New-RDSessionCollection** cmdlet creates a session collection that consists of one or more Remote Desktop Session Host (RD Session Host) servers.
Users can connect to RD Session Host servers in a session collection to run programs, save files, and use resources on those servers.

## EXAMPLES

### Example 1: Create a session collection
```
PS C:\> New-RDSessionCollection -CollectionName "Session Collection 02" -SessionHost @("RDSH01.Contoso.com"," RDSH02.Contoso.com") -CollectionDescription "Session collection for West office hosts." -ConnectionBroker "RDCB.Contoso.com"
```

This command creates a session collection named Session Collection 02 in the Remote Desktop deployment that has the RD Connection Broker server named RDCB.Contoso.com.
The collection includes the RD Session Host servers named RDSH01.Contoso.com and RDSH02.Contoso.com.
The command specifies a description of the new collection.

## PARAMETERS

### -AutoAssignUser
Indicates that this cmdlet enables automatic session desktop assignments for a personal session collection.

```yaml
Type: SwitchParameter
Parameter Sets: PersonalSessionCollection
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CollectionDescription


```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CollectionName


```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionBroker


```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GrantAdministrativePrivilege
Indicates that the server grants administrative privileges to the user account that the server assigns to a given personal virtual desktop.
This parameter applies only to personal virtual desktop collections.

```yaml
Type: SwitchParameter
Parameter Sets: PersonalSessionCollection
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PersonalUnmanaged


```yaml
Type: SwitchParameter
Parameter Sets: PersonalSessionCollection
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PooledUnmanaged


```yaml
Type: SwitchParameter
Parameter Sets: PooledSessionCollection
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SessionHost


```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.RemoteDesktopServices.Management.RDSessionCollection

## NOTES

## RELATED LINKS

[Get-RDSessionCollection](./Get-RDSessionCollection.md)

[Remove-RDSessionCollection](./Remove-RDSessionCollection.md)

