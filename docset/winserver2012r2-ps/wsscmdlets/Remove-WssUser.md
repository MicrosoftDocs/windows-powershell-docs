---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Remove-WssUser
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 5ED73E5D-95B5-40AD-848A-68E95D4F5F67
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Remove-WssUser

## SYNOPSIS
Deletes a user.

## SYNTAX

```
Remove-WssUser -Name <String> [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WssUser** cmdlet deletes a user from a sbs_sbs8_2 server.

## EXAMPLES

### Example 1: Delete a user
```
PS C:\> Remove-WssUser -Name "SarahJones"
```

This command deletes a user from WSS by using the logon name.

## PARAMETERS

### -Name
Specifies the logon name of a user.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WssUser](./Add-WssUser.md)

[Get-WssUser](./Get-WssUser.md)

