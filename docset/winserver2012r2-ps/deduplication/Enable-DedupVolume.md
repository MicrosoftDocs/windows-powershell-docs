---
external help file: DedupVolume.cdxml-help.xml
Module Name: Deduplication
online version: 
schema: 2.0.0
title: Enable-DedupVolume
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 4A752894-524D-4A64-8483-F06A73AB0ED0
---

# Enable-DedupVolume

## SYNOPSIS
Enables data deduplication on one or more volumes.

## SYNTAX

```
Enable-DedupVolume [-Volume] <String[]> [-DataAccess] [-UsageType <UsageType>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-DedupVolume** cmdlet enables data deduplication on one or more volumes .
You can use the Set-DedupVolume cmdlet to customize the data deduplication settings.
Data deduplication is disabled by default.
Data deduplication is not supported for certain volumes, such as any volume that is not a NTFS file system or any volume that is smaller than 2 GB.

## EXAMPLES

### Example 1: Enable data deduplication on volumes
```
PS C:\>Enable-DedupVolume -Volume "D:","E:","F:"
```

This command enables data deduplication on volumes D:, E:, and F:.
This command does not specify a value for the **UsageType** parameter, and, therefore, the cmdlet uses defaults for general purpose file server operations.

### Example 2: Enable data deduplication on a volume for Hyper-V storage
```
PS C:\>Enable-DedupVolume -Volume D: -UsageType HyperV
```

This command enables data duplication on the D: volume, to be used for Hyper-V storage.

### Example 3: Enable data deduplication on a volume by using a GUID
```
PS C:\>Enable-DedupVolume -Volume \\?\Volume{26a21bda-a627-11d7-9931-806e6f6e6963}\
```

This command enables data deduplication for the volume that has the GUID 26a21bda-a627-11d7-9931-806e6f6e6963.

### Example 4: Resume IO activity on a specified volume
```
PS C:\>Enable-DedupVolume -Volume X: -DataAccess
```

This command resumes IO activity for data deduplication on the specified volume. 
Effectively, this command causes the data deduplication file system mini-filter to attach to the specified volume

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete. 

The cmdlet immediately returns an object that represents the job and then displays the command prompt. 
You can continue to work in the session while the job completes. 
To manage the job, use the `*-Job` cmdlets. 
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet. 

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -DataAccess
Indicates that data access to deduplicated files on the volume is enabled.

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

### -UsageType
Specifies the expected type of workload for the volume.
The cmdlet sets several low-level settings to default values that are appropriate to the usage type that you specify.
If you specify this parameter for a volume that already has data deduplication enabled, the cmdlet modifies the settings to the appropriate default values.
If you run this cmdlet on a volume that already has data deduplication enabled but do not specify this parameter, the cmdlet does not change the usage type.
The acceptable values for this parameter are:


     -- HyperV.
A volume for Hyper-V storage. 

     -- Default.
A general purpose volume.
If you do not specify a value for this parameter, the cmdlet uses a value of Default.


If you specify a value of HyperV, the computer that has data deduplication enabled cannot be the same computer that runs Hyper-V.
The two computers must communicate remotely.

```yaml
Type: UsageType
Parameter Sets: (All)
Aliases: 
Accepted values: Default, HyperV

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Volume
Specifies an array of system volumes.
Specify one or more volume IDs, drive letters (such as D:), or volume GUID pathnames (using the form \\\\?\Volume{{GUID}}\\).
Separate multiple volumes with a comma.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Path, Name, DeviceId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Disable-DedupVolume](./Disable-DedupVolume.md)

[Get-DedupVolume](./Get-DedupVolume.md)

[Set-DedupVolume](./Set-DedupVolume.md)

