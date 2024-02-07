---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/enable-storagemaintenancemode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-StorageMaintenanceMode
---

# Enable-StorageMaintenanceMode

## SYNOPSIS
Enables storage maintenance mode on a device.

## SYNTAX

```
Enable-StorageMaintenanceMode -InputObject <CimInstance> [-IgnoreDetachedVirtualDisks]
 [-ValidateVirtualDisksHealthy <Boolean>] [-Model <String>] [-Manufacturer <String>] [-CimSession <CimSession>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-StorageMaintenanceMode** cmdlet enables storage maintenance mode on a **PhysicalDisk** device.

You can use this cmdlet on storage fault domains, which include **PhysicalDisk**, **Enclosure**, and **SSU**, that are part of a Storage Spaces pool or virtual disk.
While a device is in maintenance mode, no input/output operations flow to that device.
Instead, if other fault domains are available and configured, other fault domains serve input/output commands.
If enabling storage maintenance mode takes the last copy of data offline for a virtual disk, this cmdlet does not enable maintenance mode.

## EXAMPLES

### Example 1: Enable maintenance mode on a physical disk
```
PS C:\>Get-PhysicalDisk -FriendlyName "Disk22" | Enable-StorageMaintenanceMode
```

This command gets a physical disk by using the Get-PhysicalDisk cmdlet, and then passes that object to the current cmdlet.
The command enables storage maintenance mode on the disk named Disk22.

### Example 2: Enable maintenance mode on an enclosure
```
PS C:\>Get-StorageEnclosure -FriendlyName "Enclosure17" | Enable-StorageMaintenanceMode
```

This command gets a storage enclosure disk by using the Get-StorageEnclosure cmdlet, and then passes that object to the current cmdlet.
The command enables storage maintenance mode on the enclosure named Enclosure17.

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
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

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

### -IgnoreDetachedVirtualDisks
Indicates that this cmdlet ignores detached virtual disks when it performs the criticality check for last data-copy and other health metrics.

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

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Manufacturer
Specifies the manufacturer of a device.
This cmdlet matches manufacturer information of physical disk devices, and places those devices in maintenance mode.

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

### -Model
Specifies the model of a physical disk device that this cmdlet places in maintenance mode.
If multiple devices fit a model string, this cmdlet places those devices in maintenance mode.

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

### -ValidateVirtualDisksHealthy
Indicates whether this cmdlet validates that all virtual disks in the fault domain to be placed in maintenance mode are healthy before it proceeds.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### MSFT_StorageFaultDomain
You can pipe a fault domain object, **PhysicalDisk**, **Enclosure**, or **SSU** to this cmdlet.

## OUTPUTS

## NOTES
* You can run this cmdlet only for fault domains that host resilient virtual disks, which include Mirror and Parity Space.
* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Disable-StorageMaintenanceMode](./Disable-StorageMaintenanceMode.md)

[Get-PhysicalDisk](./Get-PhysicalDisk.md)

[Get-StorageEnclosure](./Get-StorageEnclosure.md)

