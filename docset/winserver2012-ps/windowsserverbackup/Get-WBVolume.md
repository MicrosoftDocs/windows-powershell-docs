---
external help file: WSBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 7C118C1F-7616-48DA-AE69-4E7B80CAE748
manager: dansimp
---

# Get-WBVolume

## SYNOPSIS
Retrieves a list of volumes.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-WBVolume [-Disk] <WBDisk> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Get-WBVolume [-AllVolumes] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Get-WBVolume [-CriticalVolumes] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Get-WBVolume [-Policy] <WBPolicy> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Get-WBVolume [-VolumePath] <String[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Get-WBVolume** cmdlet retrieves a list of volumes.
Use this cmdlet to display volumes included in the **WBPolicy** object, all critical volumes, all volumes, or volumes in the **WBDisk** object.
You can also use this cmdlet to get a **WBVolume** object of a volume by using the drive letter of that volume.

To use this and any other Windows Server 2012 Backup cmdlets, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Get a list of volumes on a disk
```
PS C:\>$Disks = Get-WBDisk PS C:\> Get-WBVolume -Disk $Disks[0]
```

This example gets all volumes present on a disk.

The first command stores the output of the Get-WBDisk cmdlet in the **$Disks** variable.
The command retrieves a list of all disks on the system.

The second command uses the Get-WBVolume cmdlet to get a list of volumes on the first disk.

### Example 2: Get a list of all volumes in the backup policy
```
PS C:\>$Policy = Get-WBPolicy PS C:\> Get-WBVolume -Policy $Policy
```

This example gets a list of all volumes that you added for backup in the **WBPolicy** object.

The first command stores the result of the Get-WBPolicy cmdlet in a variable named **$Policy**.

The second command gets the volumes from the **$Policy** variable.

### Example 3: Get volumes for a specific drive letter
```
PS C:\> Get-WBVolume -VolumePath E:
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
Indicates whether to list all volumes included in the backup policy.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CriticalVolumes
Indicates whether to list only critical volumes, such as volumes that contain operating system files and components.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Disk
Indicates whether to list only volumes associated with a certain disk.

```yaml
Type: WBDisk
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: OnDisk

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -Policy
Specifies the policy contained in the **WBPolicy** object to display.

```yaml
Type: WBPolicy
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: InPolicy

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -VolumePath
Specifies a volume drive letter for the volume where you will store the backups.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

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
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### WBPolicy,WBDisk,string
The Get-WBVolume cmdlet queries the **WBPolicy** object and the **WBDisk** object, and it references a string that specifies a path to the volumes where you will store the backups.

Depending on the input parameters, you can use the Get-WBVolume cmdlet to query the **WBPolicy** object for a list of volumes specified for backup, query the **WBDisk** object for a list of volumes present on a particular disk, or get a **WBVolume** object of the volume that the string specifies **VolumePath** parameter.

In addition, you can use the Get-WBVolume cmdlet with the parameters **CriticalVolumes** and **AllVolumes** to get the **WBVolume** list of all critical volumes on the system and all the volumes on the system, respectively.

## OUTPUTS

### WBVolume []
The Get-WBVolume cmdlet displays the array of volumes in the **WBPolicy** object.

## NOTES
* You can add the volumes that you get from  Get-WBVolume to the **WBPolicy** object by using the Add-WBVolume cmdlet to specify them as volumes to be backed up, or by using the New-WBBackupTarget cmdlet to specify them as backup storage locations.

  

## RELATED LINKS

[Add-WBVolume](./Add-WBVolume.md)

[Get-WBPolicy](./Get-WBPolicy.md)

[Remove-WBVolume](./Remove-WBVolume.md)

