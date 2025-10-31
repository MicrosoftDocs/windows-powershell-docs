---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-storageadvancedproperty?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-StorageAdvancedProperty
---

# Get-StorageAdvancedProperty

## SYNOPSIS
Gets the advanced properties on a storage device.

## SYNTAX

```
Get-StorageAdvancedProperty -PhysicalDisk <CimInstance> [<CommonParameters>]
```

## DESCRIPTION
The **Get-StorageAdvancedProperty** cmdlet gets the advanced properties of a storage device.
For example, Get-PhysicalDisk gets the most commonly used attributes of a physical disk such as **CanPool**.
To get the cache (**IsDeviceCacheEnabled**) and power protection (**IsPowerProtected**) settings for a physical disk, you can pass a **PhysicalDisk** object to the **Get-StorageAdvancedProperty** cmdlet.

## EXAMPLES

### Example 1: Get advanced storage properties of a physical disk
```
PS C:\>Get-PhysicalDisk | Get-StorageAdvancedProperty
FriendlyName          SerialNumber    IsPowerProtected IsDeviceCacheEnabled
------------          ------------    ---------------- --------------------
MTFDWSC128MAM-1J1     1247091D111W                True                False
WDC WD10EZWC-60ZF5A0  WD-WCC1S1822719             True                False
WDC WD10EZWC-60ZF5A0  WD-WCC1S1634655             True                False
```

This command uses the Get-PhysicalDisk cmdlet to get all physical disks, and uses the pipeline operator to pass them to **Get-StorageAdvancedProperty** to get the advanced storage properties **IsPowerProtected** and **IsDeviceCacheEnabled** for the physical disks.

### Example 2: Get advanced storage properties for the first physical disk in an array
```
PS C:\>Get-StorageAdvancedProperty -PhysicalDisk (Get-PhysicalDisk)[0]
FriendlyName          SerialNumber    IsPowerProtected IsDeviceCacheEnabled
------------          ------------    ---------------- --------------------
MTFDWSC128MAM-1J1     1247091D111W                True                False
```

This command gets the advanced storage properties **IsPowerProtected** and **IsDeviceCacheEnabled** for the first **PhysicalDisk** object in the array of returned physical disks.

## PARAMETERS

### -PhysicalDisk
Specifies an array of physical disk objects.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PhysicalDiskAdvancedProperties
The cmdlet gets the advanced properties for **PhysicalDisk** objects: **IsPowerProtected** and **IsDeviceCacheEnabled**.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-PhysicalDisk](./Get-PhysicalDisk.md)

