---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssPersonalFolder
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 1B93B0A8-A34C-4AD6-82BD-733737EF07F2
ms.author: v-kaunu
ms.reviewer: brianlic
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

