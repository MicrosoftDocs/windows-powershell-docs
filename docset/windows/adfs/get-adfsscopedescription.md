---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: brianlic
author: brianlic-msft-msft
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-AdfsScopeDescription
ms.assetid: AC797B03-44E5-4408-9354-82DD42896E9C
---

# Get-AdfsScopeDescription

## SYNOPSIS
Gets a description for a scope in AD FS.

## SYNTAX

```
Get-AdfsScopeDescription [[-Name] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsScopeDescription** cmdlet gets scope descriptions that represent the scope of access granted to resources and applications in Active Directory Federation Services (AD FS).

## EXAMPLES


## PARAMETERS

### -Name
Specifies an array of names of scope description to get.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AdfsScopeDescription](./Add-AdfsScopeDescription.md)

[Remove-AdfsScopeDescription](./Remove-AdfsScopeDescription.md)

[Set-AdfsScopeDescription](./Set-AdfsScopeDescription.md)

