---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: Get-WebGlobalModule
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: C6C4C8B2-C767-4E0A-A39E-97ACB9EE153E
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WebGlobalModule

## SYNOPSIS
Gets the global modules configured in IIS, or information about a specific module.

## SYNTAX

```
Get-WebGlobalModule [[-Name] <String>] [-Image <String>] [-Precondition <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebGlobalModule** cmdlet gets the global modules configured in Internet Information Services (IIS), or information about a specific module.

## EXAMPLES

### Example 1: Getting configuration information about a module
```
IIS:\>Get-WebGlobalModule -Name "UriCacheModule"
```

This command returns information about the configuration of the module named UriCacheModule.

## PARAMETERS

### -Image
Specifies the name of the image file associated with the module.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of a module about which this cmdlet gets information.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Precondition
Specifies a precondition for the module.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-WebGlobalModule](./Disable-WebGlobalModule.md)

[Enable-WebGlobalModule](./Enable-WebGlobalModule.md)

[New-WebGlobalModule](./New-WebGlobalModule.md)

[Remove-WebGlobalModule](./Remove-WebGlobalModule.md)

[Set-WebGlobalModule](./Set-WebGlobalModule.md)

