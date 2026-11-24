---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageCmdlets.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-storagereliabilitycounter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-StorageReliabilityCounter
---

# Get-StorageReliabilityCounter

## SYNOPSIS
Gets storage reliability counters.

## SYNTAX

### ByPhysicalDisk
```
Get-StorageReliabilityCounter -PhysicalDisk <CimInstance> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByDisk
```
Get-StorageReliabilityCounter -Disk <CimInstance> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-StorageReliabilityCounter** cmdlet gets the storage reliability counters for the specified disk or physical disk.
These counters include information about such things as the device temperature, errors, wear, and length of time the device has been in use.

## EXAMPLES

### Example 1: Get the counters for a specified physical disk
```
PS C:\>Get-PhysicalDisk -FriendlyName "PhysicalDisk8" | Get-StorageReliabilityCounter | Format-List

ObjectId                : {e24dbc00-a448-11e1-a100-806e6f6e6963}:reliabilitycounter
PassThroughClass        :
PassThroughIds          :
PassThroughNamespace    :
PassThroughServer       :
UniqueId                : {e24dbc00-a448-11e1-a100-806e6f6e6963}:reliabilitycounter
DeviceId                : 8
LoadUnloadCycleCount    : 224
LoadUnloadCycleCountMax : 300000
ManufactureDate         : Year: 2011 Week: 33
PowerOnHours            : 0
ReadErrorsCorrected     : 0
ReadErrorsTotal         : 0
ReadErrorsUncorrected   : 0
StartStopCycleCount     : 80
StartStopCycleCountMax  : 10000
Temperature             : 28
TemperatureMax          : 68
Wear                    :
WriteErrorsCorrected    : 0
WriteErrorsTotal        : 0
WriteErrorsUncorrected  : 0
PSComputerName          :
```

This command gets the physical disk named PhysicalDisk8, and uses the pipeline operator to pass it to Get-StorageReliabilityCounter, which gets all of its storage reliability counters through another pipeline with Format-List.

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
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Disk
Specifies a disk for which to get storage reliability counters.

```yaml
Type: CimInstance
Parameter Sets: ByDisk
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PhysicalDisk
Specifies the physical disk object for which to get storage reliability counters.
Enter a PhysicalDisk CIM object.

PhysicalDisk objects represent physical disks attached to a storage subsystem and located in a storage pool.

```yaml
Type: CimInstance
Parameter Sets: ByPhysicalDisk
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
You can pipe an MSFT_PhysicalDisk object to the *PhysicalDisk* parameter to get the storage reliability counters for the specified physical disk.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Disk
You can pipe an MSFT_Disk object to the *Disk* parameter to get the storage reliability counters for the specified disk.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageReliabilityCounter
The **Get-StorageReliabilityCounter** cmdlet returns a StorageReliabilityCounter object, or an array of StorageReliabilityCounter objects.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-Disk](./Get-Disk.md)

[Get-PhysicalDisk](./Get-PhysicalDisk.md)

