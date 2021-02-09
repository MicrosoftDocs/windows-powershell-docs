---
external help file: AssignedAccess-help.xml
Module Name: AssignedAccess
online version: 
schema: 2.0.0
title: Get-AssignedAccess
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 9BCF8CA4-5B35-48F5-AF23-D4BD83B2BB0B
---

# Get-AssignedAccess

## SYNOPSIS
Retrieves the current configuration for assigned access.

## SYNTAX

```
Get-AssignedAccess [<CommonParameters>]
```

## DESCRIPTION
The **Get-AssignedAccess** cmdlet retrieves the current configuration for assigned access, including the user name, user SID, app friendly name, and app ID.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-AssignedAccess

User Name: MYPC\UserName
User SID:  S-1-5-21-594534509-2542345234-234523453-1004
AUMID:     Microsoft.Media.PlayReadyClient_2.3.1678.0_x64__8wekyb3d8bbwe
App Name:  Microsoft.Media.PlayReadyClient
```

This example shows how to retrieve the current configuration for assigned access.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Set-AssignedAccess](./Set-AssignedAccess.md)

[Clear-AssignedAccess](./Clear-AssignedAccess.md)

