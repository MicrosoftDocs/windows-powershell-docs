---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Export-UevConfiguration
---

# Export-UevConfiguration

## SYNOPSIS
Exports the uev_tla configuration.

## SYNTAX

```
Export-UevConfiguration [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Export-UevConfiguration** cmdlet exports the uev_1 computer configuration to a settings migration (.uev) file.
The cmdlet exports all uev_tla agent settings for all users on the computer.

## EXAMPLES

### Example 1: Export the UE-V configuration
```
PS C:\> Export-UevConfiguration -Path "ContosoUev.uev"
```

This command exports the uev_tla computer configuration to the settings migration file named ContosoUev.uev.

## PARAMETERS

### -Path
Specifies the path of the settings migration file.
The cmdlet exports the uev_tla configuration to the settings migration file that you specify.
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


