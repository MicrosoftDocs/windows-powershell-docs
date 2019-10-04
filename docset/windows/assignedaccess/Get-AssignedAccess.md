---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: AssignedAccess-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-AssignedAccess
ms.reviewer:
ms.assetid: 9BCF8CA4-5B35-48F5-AF23-D4BD83B2BB0B
---

# Get-AssignedAccess

## SYNOPSIS
Gets the current configuration for assigned access.

## SYNTAX

```
Get-AssignedAccess [<CommonParameters>]
```

## DESCRIPTION
The **Get-AssignedAccess** cmdlet gets the current configuration for assigned access, including the user name, user SID, app friendly name, and app ID.

## EXAMPLES

### Example 1: Get the configuration for assigned access
```
PS C:\> Get-AssignedAccess

User Name: MYPC\UserName
User SID:  S-1-5-21-594534509-2542345234-234523453-1004
AUMID:     Microsoft.Media.PlayReadyClient_2.3.1678.0_x64__8wekyb3d8bbwe
App Name:  Microsoft.Media.PlayReadyClient
```

This command gets the current configuration for assigned access.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Clear-AssignedAccess](./Clear-AssignedAccess.md)

[Set-AssignedAccess](./Set-AssignedAccess.md)

