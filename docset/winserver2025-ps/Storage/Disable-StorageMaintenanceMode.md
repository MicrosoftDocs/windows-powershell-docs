---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/disable-storagemaintenancemode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-StorageMaintenanceMode
---

# Disable-StorageMaintenanceMode

## SYNOPSIS
Disables storage maintenance mode on a fault domain.

## SYNTAX

```
Disable-StorageMaintenanceMode -InputObject <CimInstance> [-Model <String>] [-Manufacturer <String>]
 [-CimSession <CimSession>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-StorageMaintenanceMode** cmdlet disables storage maintenance mode on a fault domain, which includes SSU, StorageEnclosure, and PhysicalDisk.

## EXAMPLES

### Example 1: Disable maintenance mode on a physical disk
```
PS C:\>Get-PhysicalDisk -FriendlyName "Disk22" | Disable-StorageMaintenanceMode
```

This command gets a physical disk by using the Get-PhysicalDisk cmdlet, and then passes that object to the current cmdlet.
The command disables storage maintenance mode on the disk named Disk22.

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
This cmdlet matches manufacturer information of physical disk devices, and disables maintenance mode on those devices.

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
Specifies the model of a physical disk device that this cmdlet removes from maintenance mode.
If multiple devices fit a model string, this cmdlet removes those devices from maintenance mode.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### MSFT_StorageFaultDomain
You can pipe a fault domain object, **PhysicalDisk**, **Enclosure**, or **SSU** to this cmdlet.

## OUTPUTS

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Enable-StorageMaintenanceMode](./Enable-StorageMaintenanceMode.md)

[Get-PhysicalDisk](./Get-PhysicalDisk.md)

