---
external help file: AssignedAccess-help.xml
Module Name: AssignedAccess
online version: 
schema: 2.0.0
title: Clear-AssignedAccess
ms.author: v-anbarr
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
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

