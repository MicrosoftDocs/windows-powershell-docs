---
external help file: AssignedAccess-help.xml
Module Name: AssignedAccess
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/assignedaccess/clear-assignedaccess?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-AssignedAccess
---

# Clear-AssignedAccess

## SYNOPSIS
Removes the user account from assigned access.

## SYNTAX

```
Clear-AssignedAccess [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Clear-AssignedAccess** cmdlet removes the user account from assigned access and returns the user to default settings.

If a user is signed in or the PC has a PS/2 keyboard, you must restart the computer to apply the changes.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Clear-AssignedAccess
```

This example shows how to remove the user account from assigned access and return the user to default settings.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

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

