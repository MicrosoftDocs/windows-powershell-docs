---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: ADFS
ms.assetid: 9CA2C1DF-DCB0-4E41-AA91-C3E2CB014E2E
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-AdfsSyncProperties
ms.reviewer:
---

# Get-AdfsSyncProperties

## SYNOPSIS
Gets synchronization properties the configuration database of AD FS.

## SYNTAX

```
Get-AdfsSyncProperties [<CommonParameters>]
```

## DESCRIPTION
The **Get-ADFSSyncProperties** cmdlet gets the synchronization properties for the configuration database of Active Directory Federation Services (AD FS).

## EXAMPLES

### Example 1: Get synchronization properties
```
PS C:\> Get-ADFSSyncProperties
```

This command gets the synchronization properties for the configuration database.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Set-AdfsSyncProperties](./Set-AdfsSyncProperties.md)

