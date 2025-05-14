---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-storagefirmwareinformation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-StorageFirmwareInformation
---

# Get-StorageFirmwareInformation

## SYNOPSIS
Gets information about firmware on a storage object.

## SYNTAX

### ByName (Default)
```
Get-StorageFirmwareInformation [-FriendlyName] <String> [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
Get-StorageFirmwareInformation -UniqueId <String> [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByInputObject
```
Get-StorageFirmwareInformation -InputObject <CimInstance[]> [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-StorageFirmwareInformation** cmdlet gets information about firmware on storage objects.
On Non-Volatile Memory Express (NVMe) devices, it lists the number of firmware slots, the active firmware image, and slots that are writeable.

## EXAMPLES

### Example 1: Get firmware information for physical disks
```
PS C:\>Get-PhysicalDisk | Get-StorageFirmwareInformation
```

This command uses the Get-PhysicalDisk cmdlet to get all physical disks in the system, and uses the pipeline operator to pass them to Get-StorageFirmwareInformation to get the firmware information for each disk.

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
Specifies an ID used to uniquely identify a **Disk** object in the system.
The ID persists through restarts.

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

### Boolean, UInt8, UInt8[], Boolean[], String[], String
This cmdlet returns the following firmware information for a storage object:

- **SupportsUpdate**.
Indicates whether the device is capable of a Windows-compliant firmware update process.
- **NumberOfSlots**.
The number of firmware slots the device has.
- **ActiveSlotId**.
Identifies the slot id that corresponds to the slot containing the currently active firmware image.
- **SlotId\[\]** - Array listing all slot IDs.
- **IsSlotWritable\[\]**.
Indicates if a firmware image can be downloaded to the slot represented by the ID in the **SlotId\[\]** array at the corresponding index.
- **FirmwareVersionInSlot\[\]**.
Array showing the firmware revision in each slot.
- **Extended Status**.
Error information from the storage provider.

## NOTES
* This cmdlet is currently limited to use on PhysicalDisk objects.
* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Update-StorageFirmware](./Update-StorageFirmware.md)

