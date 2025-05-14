---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
Module Name: UEV
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/uev/update-uevtemplate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-UevTemplate
---

# Update-UevTemplate

## SYNOPSIS
Updates settings location templates in UE-V.

## SYNTAX

### Path (Default)
```
Update-UevTemplate [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LiteralPath
```
Update-UevTemplate -LiteralPath <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Update-UevTemplate** cmdlet updates settings location templates in Microsoft User Experience Virtualization (UE-V).
In order for the cmdlet to update a template, the new template must have a higher value for template version.

You must have administrative credentials to run this cmdlet.

## EXAMPLES

### Example 1: Update a template
```
PS C:\> Update-UevTemplate -Path "MicrosoftCalculator.xml"
```

This command updates the settings location template specified in the current directory.

### Example 2: Update templates by specifying a path
```
PS C:\> Update-UevTemplate -Path "Microsoft*.xml"
```

This command updates all settings location templates in the current directory that match the specified string.

### Example 3: Update a template by specifying a literal path
```
PS C:\> Update-UevTemplate -LiteralPath "C:\Program Files\Microsoft User Experience Virtualization\Templates\MicrosoftCalculator.xml"
```

This command updates a settings location template by specifying a literal path to the template file.

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
The cmdlet updates the settings location templates that have the literal paths that you specify.

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
The cmdlet updates the settings location templates that have the paths that you specify.
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
An array of paths to settings location templates.

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-UevTemplate](./Disable-UevTemplate.md)

[Enable-UevTemplate](./Enable-UevTemplate.md)

[Get-UevTemplate](./Get-UevTemplate.md)

[Register-UevTemplate](./Register-UevTemplate.md)

[Test-UevTemplate](./Test-UevTemplate.md)

[Unregister-UevTemplate](./Unregister-UevTemplate.md)

