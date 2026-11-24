---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/add-wbvolume?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WBVolume
---

# Add-WBVolume

## SYNOPSIS
Adds the list of source volumes to the backup policy.

## SYNTAX

```
Add-WBVolume [-Policy] <WBPolicy> [-Volume] <WBVolume[]> [<CommonParameters>]
```

## DESCRIPTION
The **Add-WBVolume** cmdlet adds a list of source volumes to a **WBPolicy** object.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Add a list of volumes to a backup policy
```
PS C:\> $Volumes = Get-WBVolume
PS C:\> $Policy = Get-WBPolicy
PS C:\> Add-WBVolume -Policy $Policy -Volume $Volumes
```

This example adds a list of volumes for backup to the **WBPolicy** object.

The first command stores the output of the [Get-WBVolume](./Get-WBVolume.md) cmdlet in the variable named $Volumes.

The second command calls the [Get-WBPolicy](./Get-WBPolicy.md) cmdlet and assigns the result to the $Policy variable.

The third command adds the volumes in the $Volumes variable to the backup policy.

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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Volume
Specifies an array of volumes to add to the **WBPolicy** object.

```yaml
Type: WBVolume[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Windows.ServerBackup.Commands.WBPolicy

### Microsoft.Windows.ServerBackup.Commands.WBVolume[]

Ths cmdlet accepts **WBVolume** objects, which contain a new list of source volumes for the backup, and **WBPolicy** objects as input.

## OUTPUTS

### System.Object

## NOTES
* The **WBPolicy** object must be in edit mode. To put the **WBPolicy** object in edit mode for a policy that you set as the scheduled backup policy, use the Get-WBPolicy cmdlet with the *Editable* parameter. The New-WBPolicy cmdlet creates a new **WBPolicy** object that is already in edit mode.

## RELATED LINKS

[Get-WBPolicy](./Get-WBPolicy.md)

[Get-WBVolume](./Get-WBVolume.md)

[New-WBPolicy](./New-WBPolicy.md)

[Remove-WBVolume](./Remove-WBVolume.md)

