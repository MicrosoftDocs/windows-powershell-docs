---
author: brianlic-msft
description: 
external help file: AssignedAccess-help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Clear-AssignedAccess
ms.assetid: DDA49653-B37F-4CB6-90DC-B5B4BB9E6886
---

# Clear-AssignedAccess

## SYNOPSIS
Removes the user account from assigned access.

## SYNTAX

```
Clear-AssignedAccess [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Clear-AssignedAccess** cmdlet removes the specified user account from assigned access and returns the user to default settings.

If a user is signed-in or the computer has a PS/2 keyboard, you must restart the computer to apply the changes.

## EXAMPLES

### Example 1: Remove the user account from assigned access
```
PS C:\> Clear-AssignedAccess
```

This command removes the user account from assigned access and returns the user to default settings.

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

