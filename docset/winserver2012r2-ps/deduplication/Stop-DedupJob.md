---
external help file: DedupJob.cdxml-help.xml
Module Name: Deduplication
online version: 
schema: 2.0.0
title: Stop-DedupJob
ms.author: v-anbarr
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 0E612593-0BB2-4977-9D90-8F98E1D042D2
---

# Stop-DedupJob

## SYNOPSIS
Cancels one or more specified data deduplication jobs.

## SYNTAX

### ByVolume (Default)
```
Stop-DedupJob [-Volume] <String[]> [[-Type] <Type[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [<CommonParameters>]
```

### ById
```
Stop-DedupJob [-Id <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Stop-DedupJob -InputObject <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-DedupJob** cmdlet cancels one or more specified data deduplication jobs.

To run this cmdlet, you must start Windows PowerShell® with the **Run as administrator** option.

## EXAMPLES

### Example 1: Stop jobs on a specified volume
```
PS C:\>Stop-DedupJob -Volume "D:"
```

This command stops the deduplication jobs on the D: volume.

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

### -Id
Identifies the job to be cancel.
This can be obtained by running the Get-DedupJob cmdlet.

```yaml
Type: String[]
Parameter Sets: ById
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the CIM instance object that represents the instance to be changed.
Enter a variable that contains the object, or type a cmdlet or expression that gets the object, such as the Get-DedupVolume cmdlet.
A service object can be piped to the Set-DedupVolume cmdlet.

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
Returns an object representing data deduplication settings you want to stop and pushes it through the pipeline to the next cmdlet.

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

### -Type
Specifies the names of one or more types of data deduplication job schedules for which to return DeduplicationJobSchedule objects.
The acceptable values for this parameter are: Optimization, GarbageCollection, Scrubbing, and Unoptimization.

```yaml
Type: Type[]
Parameter Sets: ByVolume
Aliases: 
Accepted values: Optimization, GarbageCollection, Scrubbing, Unoptimization

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Volume
Specifies one or more file system volumes on which to cancel one or more named data deduplication jobs.
Enter one or more volume IDs, drive letters (such as `D:`), or volume GUID pathnames (using the form `\\\\?\Volume{{GUID}}\\`).
Separate multiple volumes with a comma.

```yaml
Type: String[]
Parameter Sets: ByVolume
Aliases: Path, Name, DeviceId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### Microsoft.Management.Infrastructure.CimInstance
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.DedupJob.Type[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Deduplication/MSFT_DedupJob
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DedupJob](./Get-DedupJob.md)

[Start-DedupJob](./Start-DedupJob.md)

