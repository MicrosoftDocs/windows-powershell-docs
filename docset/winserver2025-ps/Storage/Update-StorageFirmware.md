---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/update-storagefirmware?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-StorageFirmware
---

# Update-StorageFirmware

## SYNOPSIS
Updates the firmware on a storage device.

## SYNTAX

### ByName (Default)
```
Update-StorageFirmware [-FriendlyName] <String> [-ImagePath <String>] [-SlotNumber <UInt16>]
 [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
Update-StorageFirmware -UniqueId <String> [-ImagePath <String>] [-SlotNumber <UInt16>]
 [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByInputObject
```
Update-StorageFirmware -InputObject <CimInstance[]> [-ImagePath <String>] [-SlotNumber <UInt16>]
 [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Update-StorageFirmware** cmdlet updates the firmware on a storage device with the specified firmware image.

You can also use **Update-StorageFirmware** to load firmware that is already on the device but in a non-active slot.
The update operation consists of a download step and an activation step that are both performed by this cmdlet.

## EXAMPLES

### Example 1: Update a physical disk
```
PS C:\>Get-PhysicalDisk -FriendlyName "PhysicalDisk0" | Update-StorageFirmware -ImagePath "C:\Users\Contoso\Desktop\Image.bin" -SlotNumber 0
```

This command uses the Get-PhysicalDisk cmdlet to get a physical disk, and then uses the pipeline operator to pass the disk to **Update-StorageFirmware**, which updates the physical disk with the firmware in Image.bin.

### Example 2: Activate a firmware image in a different slot
```
PS C:\>Get-PhysicalDisk -FriendlyName "PhysicalDisk1" | Update-StorageFirmware -SlotNumber 2
```

This command uses the Get-PhysicalDisk cmdlet to get a physical disk, and then uses the pipeline operator to pass the disk to **Update-StorageFirmware**, which activates the firmware in slot 2.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession


```yaml
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName


```yaml
Type: String
Parameter Sets: ByName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ImagePath


```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SlotNumber


```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit


```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UniqueId
Specifies an array of IDs, as strings.

```yaml
Type: String
Parameter Sets: ByUniqueId
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### String
This cmdlet returns extended status error information as a **String** from the storage provider.

## NOTES
* This cmdlet  currently operates on physical disks only.
* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-StorageFirmwareInformation](./Get-StorageFirmwareInformation.md)

