---
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
online version: 
schema: 2.0.0
title: Remove-WBSystemState
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: B07897FC-4CAF-4F23-AD01-6D960775C421
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Remove-WBSystemState

## SYNOPSIS
Removes the system state components from the backup policy.

## SYNTAX

```
Remove-WBSystemState [-Policy] <WBPolicy> [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WBSystemState** cmdlet removes the system state components from a policy contained in the **WBPolicy** object.
Depending on what the **WBPolicy** object includes, you may still backup some of the components that are part of the system state, but you may not be able to use the components in a system state recovery.

The **WBPolicy** object must be in edit mode.
To put the **WBPolicy** object in edit mode for a policy that is the scheduled backup policy, use the Get-WBPolicy cmdlet with the **Editable** parameter.
The New-WBPolicy cmdlet creates a new **WBPolicy** object that is already in edit mode.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Remove system state from the backup policy
```
PS C:\> $Policy = Get-WBPolicy
PS C:\> Remove-WBSystemState -Policy $Policy
```

This example removes the system state components from the **WBPolicy** object.

The first command stores the results of the Get-WBPolicy cmdlet in the variable named **$Policy**.

The second command removes system state components from the backup policy in the variable **$Policy**.

## PARAMETERS

### -Policy
Specifies the backup policy **WBPolicy** object to update.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### WBPolicy
The Remove-WBSystemState cmdlet queries the **WBPolicy** object to determine whether the **WBSystemState** object is present.
The cmdlet does nothing if the **WBSystemState** object is not already present.
The cmdlet removes the **WBSystemState** object if it is present.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Add-WBSystemState](./Add-WBSystemState.md)

[Get-WBPolicy](./Get-WBPolicy.md)

[Get-WBSystemState](./Get-WBSystemState.md)

