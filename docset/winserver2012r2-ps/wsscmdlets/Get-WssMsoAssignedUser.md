---
author: Kateyanne
description: 
external help file: WssCmdlets.dll-Help.xml
manager: jasgro
Module Name: WSSCmdlets
ms.author: v-kaunu
ms.date: 12/05/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssmsoassigneduser?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssMsoAssignedUser
---

# Get-WssMsoAssignedUser

## SYNOPSIS
Gets the online service account for a user.

## SYNTAX

```
Get-WssMsoAssignedUser [[-WssUserName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssMsoAssignedUser** cmdlet gets the online service account assigned to a local network user account from aad_1.
If you do not specify a user, the cmdlet gets all online service accounts.

## EXAMPLES

### Example 1: Get a Microsoft account
```
PS C:\> Get-WssMsoAssignedUser -WssUserName "DavidChew"
```

This command gets the online service account for the user account named DavidChew.

### 1:
```
PS C:\>
```

## PARAMETERS

### -WssUserName
Specifies the name of a user account.
The cmdlet gets the online service account that corresponds to the user account that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
WssUserName
Type: System.String
Description: local network account name of user

## OUTPUTS

## NOTES

## RELATED LINKS

[Rename-WssMsoAssignedUser](./Rename-WssMsoAssignedUser.md)

[Get-WssMsoAssignedGroup](./Get-WssMsoAssignedGroup.md)

