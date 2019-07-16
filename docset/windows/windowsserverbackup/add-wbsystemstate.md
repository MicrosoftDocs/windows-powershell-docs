---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/27/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Add-WBSystemState
ms.reviewer:
ms.assetid: D07120D5-2D09-439C-B265-3FA1B5387302
---

# Add-WBSystemState

## SYNOPSIS
Adds the system state components to the backup policy.

## SYNTAX

```
Add-WBSystemState [-Policy] <WBPolicy> [<CommonParameters>]
```

## DESCRIPTION
The **Add-WBSystemState** cmdlet adds the system state components to a policy contained in the specified **WBPolicy** object.
Use backups created through this policy to perform a system state recovery.

The **WBPolicy** object must be in edit mode.
To put the **WBPolicy** object in edit mode for a policy that is set as the scheduled backup policy, use the [Get-WBPolicy](./Get-WBPolicy.md) cmdlet with the *Editable* parameter.
The [New-WBPolicy](./New-WBPolicy.md) cmdlet creates a new **WBPolicy** object that is already in edit mode.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Add system state to the backup policy
```
PS C:\> $Policy = Get-WBPolicy -Editable
PS C:\> Add-WBSystemState -Policy $Policy
```

This example adds a setting to the **WBPolicy** object to include the system state in backups that you create by using this policy.

The first command stores the result of the **Get-WBPolicy** cmdlet in the variable named $Policy.

The second command adds the system state to the backup policy in the $Policy variable.

## PARAMETERS

### -Policy
Specifies a **WBPolicy** object that contains the backup policy to update.

```yaml
Type: WBPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### WBPolicy
This cmdlet accepts a **WBPolicy** object as input.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-WBPolicy](./Get-WBPolicy.md)

[Get-WBSystemState](./Get-WBSystemState.md)

[Remove-WBSystemState](./Remove-WBSystemState.md)

