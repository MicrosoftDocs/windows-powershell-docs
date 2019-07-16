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
title: Get-WBSystemState
ms.reviewer:
ms.assetid: BD09EDAF-39BB-44B4-A8AE-3971D818CC4B
---

# Get-WBSystemState

## SYNOPSIS
Gets a Boolean value that indicates whether system state recovery was added to the backup policy.

## SYNTAX

```
Get-WBSystemState [-Policy] <WBPolicy> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WBSystemState** cmdlet gets a Boolean value that indicates whether the ability to perform system state recoveries along with the backups was added to the **WBPolicy** object.
If the system state is not in the list of items to be backed up, use the [Add-WBSystemState](./Add-WBSystemState.md) cmdlet to add it to the list.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Get the system state setting from the backup
```
PS C:\> $Policy = Get-WBPolicy
PS C:\> Get-WBSystemState -Policy $Policy
```

This example displays a Boolean value that indicates whether the system state setting was added to the **WBPolicy** object that is stored in the variable named $Policy.
The system state setting enables you to use the backups to perform system state recoveries.

The first command stores the result of the [Get-WBPolicy](./Get-WBPolicy.md) cmdlet to the variable named $Policy.

The second command displays the result of the **Get-WBSystemState** cmdlet using the variable named $Policy.

## PARAMETERS

### -Policy
Specifies a **WBPolicy** object that contains the backup policy to display.

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
This cmdlet queries the **WBPolicy** object for the backup policy.

## OUTPUTS

### boolean
This cmdlet returns a Boolean value to indicate whether the system state is included in the **WBPolicy** object.

## NOTES

## RELATED LINKS

[Add-WBSystemState](./Add-WBSystemState.md)

[Get-WBPolicy](./Get-WBPolicy.md)

[New-WBPolicy](./New-WBPolicy.md)

[Remove-WBSystemState](./Remove-WBSystemState.md)

