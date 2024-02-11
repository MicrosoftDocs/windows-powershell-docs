---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
Module Name: UEV
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/uev/enable-uevtemplate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-UevTemplate
---

# Enable-UevTemplate

## SYNOPSIS
Enables a settings location template.

## SYNTAX

```
Enable-UevTemplate [-ID] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-UevTemplate** cmdlet enables a settings location template for the current user of the computer.

## EXAMPLES

### Example 1: Enable a specific template
```
PS C:\> Enable-UevTemplate -ID "MicrosoftCalculator6"
```

This command enables a settings location template that has the specified ID for the current user.

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

### -ID
Specifies the ID of a settings location template.
The cmdlet enables the template that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: TemplateID

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### string
The settings location template ID.

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-UevTemplate](./Disable-UevTemplate.md)

[Get-UevTemplate](./Get-UevTemplate.md)

[Register-UevTemplate](./Register-UevTemplate.md)

[Test-UevTemplate](./Test-UevTemplate.md)

[Unregister-UevTemplate](./Unregister-UevTemplate.md)

[Update-UevTemplate](./Update-UevTemplate.md)

