---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/get-wbvolume?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WBVolume
---

# Get-WBVolume

## SYNOPSIS
Gets a list of volumes.

## SYNTAX

### Disk (Default)
```
Get-WBVolume [-Disk] <WBDisk> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Policy
```
Get-WBVolume [-Policy] <WBPolicy> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CriticalVolumes
```
Get-WBVolume [-CriticalVolumes] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AllVolumes
```
Get-WBVolume [-AllVolumes] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VolumePath
```
Get-WBVolume [-VolumePath] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WBVolume** cmdlet gets a list of volumes.
Use this cmdlet to display volumes included in the **WBPolicy** object, all critical volumes, all volumes, or volumes in the **WBDisk** object.
You can also use this cmdlet to get a **WBVolume** object of a volume by using the drive letter of that volume.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Get a list of volumes on a disk
```
PS C:\> $Disks = Get-WBDisk
PS C:\> Get-WBVolume -Disk $Disks[0]
```

This example gets all volumes present on a disk.

The first command stores the output of the [Get-WBDisk](./Get-WBDisk.md) cmdlet in the $Disks variable.
The command gets a list of all disks on the system.

The second command uses the **Get-WBVolume** cmdlet to get a list of volumes on the first disk.

### Example 2: Get a list of all volumes in the backup policy
```
PS C:\> $Policy = Get-WBPolicy
PS C:\> Get-WBVolume -Policy $Policy
```

This example gets a list of all volumes that you added for backup in the **WBPolicy** object.

The first command stores the result of the [Get-WBPolicy](./Get-WBPolicy.md) cmdlet in a variable named $Policy.

The second command gets the volumes from the $Policy variable.

### Example 3: Get volumes for a specific drive letter
```
PS C:\> Get-WBVolume -VolumePath "E:"
```

This command gets the **WBVolume** object for the volume that uses drive letter E:.

### Example 4: Get all volumes on a computer
```
PS C:\> Get-WBVolume -AllVolumes
```

This command gets a list of **WBVolume** objects of all the volumes present on the computer.

### Example 5: Get all critical volumes on a computer
```
PS C:\> Get-WBVolume -CriticalVolumes
```

This command gets the list of all the critical volumes present on the computer.
Critical volumes are volumes that contain operating system components and files.

## PARAMETERS

### -AllVolumes
Indicates that this cmdlet lists all volumes included in the backup policy.

```yaml
Type: SwitchParameter
Parameter Sets: AllVolumes
Aliases:

Required: True
Position: 0
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

### -CriticalVolumes
Indicates that this cmdlet lists only critical volumes, such as volumes that contain operating system files and components.

```yaml
Type: SwitchParameter
Parameter Sets: CriticalVolumes
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Disk
Specifies a volume that is associated with a certain disk.

```yaml
Type: WBDisk
Parameter Sets: Disk
Aliases: OnDisk

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Policy
Specifies the policy contained in the **WBPolicy** object to display.

```yaml
Type: WBPolicy
Parameter Sets: Policy
Aliases: InPolicy

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -VolumePath
Specifies an array of volume drive letters for the volume where you store the backups.

```yaml
Type: String[]
Parameter Sets: VolumePath
Aliases:

Required: True
Position: 0
Default value: None
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

### Microsoft.Windows.ServerBackup.Commands.WBDisk

### Microsoft.Windows.ServerBackup.Commands.WBPolicy

This cmdlet queries the **WBPolicy** object and the **WBDisk** object, and it references a string that specifies a path to the volumes where you will store the backups.

Depending on the input parameters, you can use this cmdlet to query the **WBPolicy** object for a list of volumes specified for backup, query the **WBDisk** object for a list of volumes present on a particular disk, or get a **WBVolume** object of the volume that the string specifies *VolumePath* parameter.

In addition, you can use this cmdlet with the parameters *CriticalVolumes* and *AllVolumes* to get the **WBVolume** list of all critical volumes on the system and all the volumes on the system, respectively.

## OUTPUTS

### System.Object

## NOTES
* You can add the volumes that you get from this cmdlet to the **WBPolicy** object by using the **Add-WBVolume** cmdlet to specify them as volumes to be backed up, or by using the **New-WBBackupTarget** cmdlet to specify them as backup storage locations.

## RELATED LINKS

[Add-WBVolume](./Add-WBVolume.md)

[Get-WBDisk](./Get-WBDisk.md)

[Get-WBPolicy](./Get-WBPolicy.md)

[Remove-WBVolume](./Remove-WBVolume.md)

