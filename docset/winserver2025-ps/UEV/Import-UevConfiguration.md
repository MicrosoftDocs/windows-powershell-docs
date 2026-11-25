---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
Module Name: UEV
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/uev/import-uevconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-UevConfiguration
---

# Import-UevConfiguration

## SYNOPSIS
Imports the UE-V configuration.

## SYNTAX

```
Import-UevConfiguration [-Path] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Import-UevConfiguration** cmdlet imports the Microsoft User Experience Virtualization (UE-V) computer configuration from a settings migration (.uev) file.
You must have administrative credentials to run this cmdlet.

## EXAMPLES

### Example 1: Import the UE-V configuration
```
PS C:\> Import-UevConfiguration -Path "ContosoUev.uev"
```

This command imports the UE-V computer configuration from the settings migration file named ContosoUev.uev.

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

### -Path
Specifies the path of the settings migration file.
The cmdlet imports the UE-V configuration from the settings migration file (.uev file) that you specify.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-UevConfiguration](./Get-UevConfiguration.md)

[Set-UevConfiguration](./Set-UevConfiguration.md)

[Clear-UevConfiguration](./Clear-UevConfiguration.md)

[Export-UevConfiguration](./Export-UevConfiguration.md)

