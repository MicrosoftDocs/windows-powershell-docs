---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Set-WssUserAccess
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: F8994BB4-0248-4B58-9FB7-F85BD7A53672
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Set-WssUserAccess

## SYNOPSIS
Modifies the user access setting.

## SYNTAX

```
Set-WssUserAccess [-GrantAccess <UserAccess>] [-RevokeAccess <UserAccess>] [-User] <User> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssUserAccess** cmdlet modifies the user access setting in sbs_sbs8_2.

## EXAMPLES

### Example 1: Modify user access
```
PS C:\> Set-WSSUserAccess -User $WSSUser -GrantAccess 2
```

This command modifies user access by granting ShareAccess to the user in the variable named **WSSUser**.

## PARAMETERS

### -GrantAccess
Specifies the access to grant to a user.
To set more than one access, you must call the cmdlet for each access.
Valid values for this parameter are:
- 1 RemoteAccess
- 2 ShareAccess
- 3 ComputerAccess
- 4 MediaAccess
- 5 AddInAccess
- 6 DashboardAccess
- 7 HomePageLinks
- 8 NetworkAlertAccess
- 9 VpnAccess

```yaml
Type: UserAccess
Parameter Sets: (All)
Aliases: 
Accepted values: RemoteAccess, ShareAccess, ComputerAccess, MediaAccess, VpnAccess, DashboardAccess, HomePageLinks, NetworkAlertAccess

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RevokeAccess
Specifies the access to revoke from a user.
Valid values for this parameter are:
- 1 RemoteAccess
- 2 ShareAccess
- 3 ComputerAccess
- 4 MediaAccess
- 5 AddInAccess
- 6 DashboardAccess
- 7 HomePageLinks
- 8 NetworkAlertAccess
- 9 VpnAccess

```yaml
Type: UserAccess
Parameter Sets: (All)
Aliases: 
Accepted values: RemoteAccess, ShareAccess, ComputerAccess, MediaAccess, VpnAccess, DashboardAccess, HomePageLinks, NetworkAlertAccess

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -User
Specifies a user object.

```yaml
Type: User
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

