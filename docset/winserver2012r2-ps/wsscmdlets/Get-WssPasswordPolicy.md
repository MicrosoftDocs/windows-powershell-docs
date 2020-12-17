---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssPasswordPolicy
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 702FCE34-362A-4187-882B-1281D91384D0
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssPasswordPolicy

## SYNOPSIS
Gets the current password policy for a server.

## SYNTAX

```
Get-WssPasswordPolicy [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssPasswordPolicy** cmdlet gets the current password policy for a server.

## EXAMPLES

### Example 1: Get the password policy for a server
```
PS C:\> Get-WssPasswordPolicy
```

This command gets the password policy from the server.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.Identity.PasswordPolicy
This cmdlet generates the password policy object for the server.

## NOTES

## RELATED LINKS

