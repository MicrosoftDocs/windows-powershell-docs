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
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wsspersonalfolder?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssPersonalFolder
---

# Get-WssPersonalFolder

## SYNOPSIS
Gets the personal folder for a user.

## SYNTAX

```
Get-WssPersonalFolder [-UserName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssPersonalFolder** cmdlet gets the personal folder for the specified user.

## EXAMPLES

### Example 1: Get a personal folder
```
PS C:\> Get-WssPersonalFolder -UserName "PattiFuller"
```

This command gets the personal folder for the account named PattiFuller.

## PARAMETERS

### -UserName
Specifies the name of a user account.
The cmdlet gets the personal folder for the account that you specify on the current server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.IO.DirectoryInfo

## NOTES

## RELATED LINKS

[New-WssPersonalFolder](./New-WssPersonalFolder.md)

