---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
Module Name: UEV
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/uev/unregister-uevtemplate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-UevTemplate
---

# Unregister-UevTemplate

## SYNOPSIS
Unregisters a settings location template from Microsoft User Experience Virtualization (UE-V).

## SYNTAX

### ParameterSetTemplateId
```
Unregister-UevTemplate [-ID] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ParameterSetAllTemplates
```
Unregister-UevTemplate [-All] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Unregister-UevTemplate** cmdlet unregisters a settings location template from Microsoft User Experience Virtualization (UE-V).
A template defines settings to synchronize between computers.
After you unregister a template, UE-V no longer synchronizes those settings.
If you try to unregister a template that is not registered, the cmdlet returns an error.

You must have administrative credentials to run this cmdlet.

## EXAMPLES

### Example 1: Unregister a template
```
PS C:\> Unregister-UevTemplate -TemplateId "MicrosoftCalculator6"
```

This command unregisters a settings location template that has the ID MicrosoftCalculator6.

### Example 2: Unregister templates for applications that match a specified string
```
PS C:\> Get-UevTemplate -Application "calc" | Unregister-UevTemplate
```

This command uses the **Get-UevTemplate** cmdlet to get all the registered settings location templates whose application name contains the specified string, and then passes them to the current cmdlet by using the pipeline operator.
The cmdlet unregisters all the templates for applications that contain the string calc.

### Example 3: Unregister all templates
```
PS C:\> Unregister-UevTemplate -All
```

This command unregisters all the settings location templates that are currently registered with UE-V.

## PARAMETERS

### -All
Indicates that the cmdlet unregisters all settings location templates.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetAllTemplates
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
The cmdlet unregisters the template that you specify.
If you specify an ID for a template that is not registered, the cmdlet returns an error.

```yaml
Type: String
Parameter Sets: ParameterSetTemplateId
Aliases: TemplateID

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

### System.String
The settings location template ID.

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-UevTemplate](./Disable-UevTemplate.md)

[Enable-UevTemplate](./Enable-UevTemplate.md)

[Get-UevTemplate](./Get-UevTemplate.md)

[Register-UevTemplate](./Register-UevTemplate.md)

[Test-UevTemplate](./Test-UevTemplate.md)

[Update-UevTemplate](./Update-UevTemplate.md)

