---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
Module Name: UEV
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/uev/register-uevtemplate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Register-UevTemplate
---

# Register-UevTemplate

## SYNOPSIS
Registers a settings location template with UE-V.

## SYNTAX

### Path (Default)
```
Register-UevTemplate [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LiteralPath
```
Register-UevTemplate -LiteralPath <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Register-UevTemplate** cmdlet registers a settings location template with Microsoft User Experience Virtualization (UE-V).
A template defines settings to synchronize between computers.
After you register a template, UE-V synchronizes the settings.
If you try to register a template that is already registered, the cmdlet returns an error.

You must have administrative credentials to run this cmdlet.

## EXAMPLES

### Example 1: Register a template
```
PS C:\> Register-UevTemplate -Path "MicrosoftCalculator.xml"
```

This command registers a template in the current directory.

### Example 2: Register multiple templates
```
PS C:\> Register-UevTemplate -Path "Microsoft*.xml"
```

This command uses a wildcard to specify multiple templates in the current directory.

### Example 3: Register all templates in a directory
```
PS C:\> Register-UevTemplate -Path "*.xml"
```

This command uses a wildcard to register all settings location templates that are in the current directory but that are not currently registered.

### Example 4: Register a template by using a literal path
```
PS C:\> Register-UevTemplate -LiteralPath "C:\Program Files\Microsoft User Experience Virtualization\Templates\MicrosoftCalculator.xml"
```

This command registers a settings location template by using the literal path of the template file.

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

### -LiteralPath
Specifies an array of literal file paths.
The cmdlet registers the settings location templates that have the literal paths that you specify.

```yaml
Type: String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies an array of file paths.
The cmdlet registers the settings location templates that have the paths that you specify.
Use wildcards to specify multiple files.

```yaml
Type: String[]
Parameter Sets: Path
Aliases: Name

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### string[]
An array of paths to the settings location templates.

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-UevTemplate](./Disable-UevTemplate.md)

[Enable-UevTemplate](./Enable-UevTemplate.md)

[Get-UevTemplate](./Get-UevTemplate.md)

[Test-UevTemplate](./Test-UevTemplate.md)

[Unregister-UevTemplate](./Unregister-UevTemplate.md)

[Update-UevTemplate](./Update-UevTemplate.md)

