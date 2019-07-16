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
title: Remove-WBVolume
ms.reviewer:
ms.assetid: 456F2FAD-E865-4499-A5AB-01DAF49DDACD
---

# Remove-WBVolume

## SYNOPSIS
Removes the volume from the backup policy.

## SYNTAX

```
Remove-WBVolume [-Policy] <WBPolicy> [-Volume] <WBVolume> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WBVolume** cmdlet removes the **WBVolume** object from the **WBPolicy** object.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Remove a volume from the backup policy
```
PS C:\> $Policy = Get-WBPolicy
PS C:\> $Volume = Get-WBVolume -VolumePath "E:"
PS C:\> Remove-WBVolume -Policy $Policy -Volume $Volume
```

This example removes the specified volume from the backup policy.
The output is the list of volumes left in the **WBPolicy** object.

The first command stores the output of [Get-WBPolicy](./Get-WBPolicy.md) in the variable named $Policy.

The second command stores the output of [Get-WBVolume](./Get-WBVolume.md) in the variable $Volume.

The third command uses **Remove-WBVolume** to remove the volumes in the variable $Volume from the backup policy object.

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

### -Policy
Specifies the **WBPolicy** object that contains the policy that this cmdlet updates.

```yaml
Type: WBPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Volume
Specifies the volume that this cmdlet removes from the policy contained in the **WBPolicy** object.

```yaml
Type: WBVolume
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### WBPolicy,WBVolume
This cmdlet removes the **WBVolume** object from the policy contained in the **WBPolicy** object.

## OUTPUTS

### WBVolume[]
This cmdlet returns a the list of **WBVolume** objects left in **WBPolicy** after the cmdlet removes the specified **WBVolume** object.

## NOTES
* The **WBPolicy** object must be in edit mode. To put the **WBPolicy** object in edit mode for a policy that you set as the scheduled backup policy, use the Get-WBPolicy cmdlet with the *Editable* parameter. The New-WBPolicy cmdlet creates a **WBPolicy** object that is already in edit mode.

  

## RELATED LINKS

[Add-WBVolume](./Add-WBVolume.md)

[Get-WBPolicy](./Get-WBPolicy.md)

[Get-WBVolume](./Get-WBVolume.md)

