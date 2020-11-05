---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Enable-WssMsoUser
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 96C37B2B-2889-40E2-98B7-1FC83CB2527B
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Enable-WssMsoUser

## SYNOPSIS
Enables an online service account.

## SYNTAX

```
Enable-WssMsoUser [-WssUserName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Enable-WssMsoUser** cmdlet enables the online service account that is assigned to a local network user account.
You can use this command after disabling an account with **Disable-WssMsoUser**.

## EXAMPLES

### Example 1: Enable an online service account
```
PS C:\> Enable-WssMsoUser -WssUserName "DavidChew"
```

This command enables the online service account that is assigned to the user account named DavidChew.

## PARAMETERS

### -WssUserName
Specifies the name of a user account.
The cmdlet enables the online service account that is assigned to the user account that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
WssUserName - the local account name of user to be enabled.

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WssMsoUser](./Add-WssMsoUser.md)

[Disable-WssMsoUser](./Disable-WssMsoUser.md)

[Get-WssMsoUser](./Get-WssMsoUser.md)

[Remove-WssMsoUser](./Remove-WssMsoUser.md)

