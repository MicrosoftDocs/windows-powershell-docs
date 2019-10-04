---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: ADFS
ms.assetid: C05237E5-0C2F-44F2-A2BE-0CF4935A3E39
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-AdfsFarmInformation
ms.reviewer:
---

# Get-AdfsFarmInformation

## SYNOPSIS
Gets AD FS behavior level and farm node information.

## SYNTAX

```
Get-AdfsFarmInformation [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsFarmInformation** cmdlet gets the current Active Directory Federation Services (AD FS) behavior level and farm node information.

## EXAMPLES

### Example 1: Get farm information
```
PS C:\> Get-AdfsFarmInformation
```

This cmdlet gets AD FS behavior level and farm node information.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-AdfsFarmInformation](./Set-AdfsFarmInformation.md)

