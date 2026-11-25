---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: AssignedAccess-help.xml
Module Name: AssignedAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/assignedaccess/clear-assignedaccess?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-AssignedAccess
---

# Clear-AssignedAccess

## SYNOPSIS
Clears assigned access configured account settings.

## SYNTAX

```
Clear-AssignedAccess [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Clear-AssignedAccess** cmdlet clears assigned access configured account settings and returns the user to default settings.

If a user is signed-in or the computer has a PS/2 keyboard, you must restart the computer to apply the changes.

Assigned Access cmdlets are supported on Windows 10 and Windows 11 client operating systems only.

## EXAMPLES

### Example 1: Clear assigned access configured settings
```
PS C:\> Clear-AssignedAccess
```

This command assigned access configured account settings  and returns the user to default settings.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-AssignedAccess](./Get-AssignedAccess.md)

[Set-AssignedAccess](./Set-AssignedAccess.md)

