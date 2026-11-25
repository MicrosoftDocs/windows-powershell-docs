---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
Module Name: UEV
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/uev/disable-uevtemplate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-UevTemplate
---

# Disable-UevTemplate

## SYNOPSIS
Disables a settings location template.

## SYNTAX

```
Disable-UevTemplate [-ID] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-UevTemplate** cmdlet disables a settings location template for the current user of the computer.
Use this cmdlet to disable a settings location template for an individual user.
To disable a settings location template for all users on the computer, use the **Unregister-UevTemplate** cmdlet.

## EXAMPLES

### Example 1: Disable a specific template
```
PS C:\> Disable-UevTemplate -ID "MicrosoftCalculator6"
```

This command disables a settings location template that has the specified ID for the current user.

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
The cmdlet disables the template that you specify.

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

[Enable-UevTemplate](./Enable-UevTemplate.md)

[Get-UevTemplate](./Get-UevTemplate.md)

[Register-UevTemplate](./Register-UevTemplate.md)

[Test-UevTemplate](./Test-UevTemplate.md)

[Unregister-UevTemplate](./Unregister-UevTemplate.md)

[Update-UevTemplate](./Update-UevTemplate.md)

