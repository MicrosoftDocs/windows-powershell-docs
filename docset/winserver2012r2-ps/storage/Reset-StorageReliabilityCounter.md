---
external help file: StorageReliabilityCounter.cdxml-help.xml
Module Name: Storage
online version: 
schema: 2.0.0
title: Reset-StorageReliabilityCounter
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 76FFF486-BBD6-462E-94C0-02F292601FA2
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Reset-StorageReliabilityCounter

## SYNOPSIS
Resets storage reliability counters for a disk.

## SYNTAX

### ByPhysicalDisk
```
Reset-StorageReliabilityCounter -PhysicalDisk <CimInstance> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### ByVirtualDisk
```
Reset-StorageReliabilityCounter -Disk <CimInstance> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [<CommonParameters>]
```

### InputObject (cdxml)
```
Reset-StorageReliabilityCounter -InputObject <CimInstance[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Reset-StorageReliabilityCounter** cmdlet resets the storage reliability counters to zero for a virtual disk or physical disk.
The cmdlet resets the following storage reliability counters for I/O operations: read latency, write latency, and flush latency.
If an unexpected issue with a disk or driver causes high latency, use this cmdlet to discount the sharp rise in latencies when you monitor I/O performance.

## EXAMPLES

### Example 1: Reset the reliability counters for two physical disks
```
PS C:\> $Counter1 = Get-StorageReliabilityCounter -PhysicalDisk (Get-PhysicalDisk "PhysicalDisk01")
PS C:\> $Counter2 = Get-StorageReliabilityCounter -PhysicalDisk (Get-PhysicalDisk "PhysicalDisk02")
PS C:\> Reset-StorageReliabilityCounter -InputObject $Counter1, $Counter2
```

The first command gets the storage reliability counters for the physical disk named PhysicalDisk01, and stores the counters in the **$Counter1** variable.

The second command gets the storage reliability counters for the physical disk named PhysicalDisk02, and stores the counters in the **$Counter2** variable.

The last command resets the storage reliability counters for the physical disks stored in **$Counter1** and **$Counter2**.

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
Specifies a disk as a **CIMInstance** object.
The cmdlet resets the storage reliability counter for the disk that you specify.
To obtain a disk, use the Get-Disk cmdlet.

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -PhysicalDisk
Specifies a physical disk as a **CIMInstance** object.
The cmdlet resets the storage reliability counter for the physical disk that you specify.
To obtain a physical disk object, use the Get-PhysicalDisk cmdlet.

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageReliabilityCounter
You can use the pipeline operator to pass an arrary of MSFT_StorageReliabilityCounter objects to the **InputObject** parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageReliabilityCounter
This cmdlet outputs an array of objects that represent storage reliability counter data.

## NOTES

## RELATED LINKS

[Get-StorageReliabilityCounter](./Get-StorageReliabilityCounter.md)

[Get-PhysicalDisk](./Get-PhysicalDisk.md)

