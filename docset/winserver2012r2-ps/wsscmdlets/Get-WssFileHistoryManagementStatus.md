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
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssfilehistorymanagementstatus?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssFileHistoryManagementStatus
---

# Get-WssFileHistoryManagementStatus

## SYNOPSIS
Gets the File History managed status of a user.

## SYNTAX

```
Get-WssFileHistoryManagementStatus [-UserName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssFileHistoryManagementStatus** cmdlet gets the File History managed status of a user.
The cmdlet returns $True if the File History setting of the user is managed by the server.

## EXAMPLES

### Example 1: Get the File History managed status of a user
```
PS C:\> Get-WssFileHistoryManagementStatus -UserName "DaveB"
```

This command gets the File History managed status of a user named DaveB.

## PARAMETERS

### -UserName
Specifies the user name of an account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: un

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

### System.Boolean
This cmdlet generates the file history managed status for a user, which is $True if the user's file history setting is managed by the server.

## NOTES

## RELATED LINKS

[Set-WssFileHistoryManagementStatus](./Set-WssFileHistoryManagementStatus.md)

[Get-WssFileHistoryConfiguration](./Get-WssFileHistoryConfiguration.md)

