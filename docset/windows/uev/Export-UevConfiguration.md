---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Export-UevConfiguration
ms.reviewer:
ms.assetid: 9A74BFA7-5684-4035-BFF0-1B9FD89B671B
---

# Export-UevConfiguration

## SYNOPSIS
Exports the UE-V configuration.

## SYNTAX

```
Export-UevConfiguration [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Export-UevConfiguration** cmdlet exports the Microsoft User Experience Virtualization (UE-V) computer configuration to a settings migration (.uev) file.
The cmdlet exports all UE-V agent settings for all users on the computer.

## EXAMPLES

### Example 1: Export the UE-V configuration
```
PS C:\> Export-UevConfiguration -Path "ContosoUev.uev"
```

This command exports the UE-V computer configuration to the settings migration file named ContosoUev.uev.

## PARAMETERS

### -Path
Specifies the path of the settings migration file.
The cmdlet exports the UE-V configuration to the settings migration file that you specify.
The extension of the settings migration file must be .uev.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-UevConfiguration](./Get-UevConfiguration.md)

[Set-UevConfiguration](./Set-UevConfiguration.md)

[Clear-UevConfiguration](./Clear-UevConfiguration.md)

[Import-UevConfiguration](./Import-UevConfiguration.md)

