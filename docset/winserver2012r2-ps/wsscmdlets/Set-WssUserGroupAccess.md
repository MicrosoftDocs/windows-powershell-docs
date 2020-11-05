---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Set-WssUserGroupAccess
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 7F535BC6-C4F0-4D22-A35F-D86FAB70F433
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Set-WssUserGroupAccess

## SYNOPSIS
Modifies access for user groups.

## SYNTAX

```
Set-WssUserGroupAccess -Name <String> [-GrantAccess <WSSGroupType>] [-RevokeAccess <WSSGroupType>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssUserGroupAccess** cmdlet modifies access for user groups.

## EXAMPLES

### Example 1: Grant ShareAccess to a group
```
PS C:\> Set-WssUserGroupAccess -Name "HRGroup" -GrantAccess 2
```

This command grants ShareAccess to the group named HRGroup.
The **GrantAccess** parameter specifies a value of 2, which corresponds to ShareAccess.

## PARAMETERS

### -GrantAccess
Specifies the access to grant.
The cmdlet grants the access that you specify to users in the user group.
To grant more than one type of access, run the cmdlet for each type to grant.
The acceptable values for this parameter are:


- 1 RemoteAccess

- 2 ShareAccess

- 3 ComputerAccess

- 4 MediaAccess

- 6 DashboardAccess

- 7 HomePageLinks

- 9 VpnAccess

```yaml
Type: WSSGroupType
Parameter Sets: (All)
Aliases: 
Accepted values: InvalidAccess, RemoteAccess, ShareAccess, ComputerAccess, MediaAccess, AddInAccess, DashboardAccess, HomePageLinks, NetworkAlertAccess, VpnAccess, InvisibleToDashboard

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a name.
The cmdlet modifies access for the group that you specify by name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RevokeAccess
Specifies the access to revoke.
The cmdlet revokes the access that you specify to users in the user group.
To revoke more than one type of access, use the cmdlet for each type to revoke.
The acceptable values for this parameter are:


- 1 RemoteAccess

- 2 ShareAccess

- 3 ComputerAccess

- 4 MediaAccess

- 6 DashboardAccess

- 7 HomePageLinks

- 9 VpnAccess

```yaml
Type: WSSGroupType
Parameter Sets: (All)
Aliases: 
Accepted values: InvalidAccess, RemoteAccess, ShareAccess, ComputerAccess, MediaAccess, AddInAccess, DashboardAccess, HomePageLinks, NetworkAlertAccess, VpnAccess, InvisibleToDashboard

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-WssUserAccess](./Set-WssUserAccess.md)

