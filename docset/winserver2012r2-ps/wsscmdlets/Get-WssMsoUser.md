---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssMsoUser
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 01E813AD-6E36-4CA7-B91D-142CB0069592
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssMsoUser

## SYNOPSIS
Gets the online service account for a user.

## SYNTAX

```
Get-WssMsoUser [[-MsoUserName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssMsoUser** cmdlet gets the online service account for a user principal name (UPN) from aad_1.
If you do not specify a UPN, the cmdlet gets all online service accounts.

## EXAMPLES

### Example 1: Get an online service account
```
PS C:\> Get-WssMsoUser -MsoUserName "DavidChew@TSQA.Contoso.com"
```

This command gets the online service account for the specified UPN.

## PARAMETERS

### -MsoUserName
Specifies a UPN.
The cmdlet gets the online service account for the UPN that you specify.

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

[Add-WssMsoUser](./Add-WssMsoUser.md)

[Disable-WssMsoUser](./Disable-WssMsoUser.md)

[Enable-WssMsoUser](./Enable-WssMsoUser.md)

[Remove-WssMsoUser](./Remove-WssMsoUser.md)

