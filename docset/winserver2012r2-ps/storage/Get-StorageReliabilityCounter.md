---
author: Kateyanne
description: 
external help file: StorageReliabilityCounter.cdxml-help.xml
manager: jasgro
Module Name: Storage
ms.author: v-kaunu
ms.date: 10/29/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/storage/get-storagereliabilitycounter?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-StorageReliabilityCounter
---

# Get-StorageReliabilityCounter

## SYNOPSIS
Gets the storage reliability counters for the disk or physical disk that you specify.

## SYNTAX

### ByPhysicalDisk
```
Get-StorageReliabilityCounter -PhysicalDisk <CimInstance> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByVirtualDisk
```
Get-StorageReliabilityCounter -Disk <CimInstance> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
Gets the storage reliability counters for the disk or physical disk that you specify.
These counters include information about such things as the device temperature, errors encountered, wear, and length of time the device has been in use.

## EXAMPLES

### Example 1: Get the counters for all physical disks
```
PS C:\>Get-PhysicalDisk | Get-StorageReliabilityCounter
```

This example pipes the output of the Get-PhysicalDisk cmdlet to the Get-StorageReliabilityCounter cmdlet, getting the counters for all physical disks.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
Specifies the disk object for which to get storage reliability counters.
Enter a Disk CIM object.

Disk objects represent disks as seen by the operating system above the storage subsystem.
Disks could be actual physical hardware directly attached to the computer, or could be virtualized storage such as a virtual disk that has been assigned to a computer and appears to the operating system as a disk.

```yaml
Type: CimInstance
Parameter Sets: ByVirtualDisk
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
You can pipe an MSFT_PhysicalDisk object to the PhysicalDisk parameter to get the storage reliability counters for the specified physical disk.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Disk
You can pipe an MSFT_Disk object to the Disk parameter to get the storage reliability counters for the specified disk.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageReliabilityCounter
The Get-StorageReliabilityCounter cmdlet returns a StorageReliabilityCounter object, or an array of StorageReliabilityCounter objects.

## NOTES

## RELATED LINKS

