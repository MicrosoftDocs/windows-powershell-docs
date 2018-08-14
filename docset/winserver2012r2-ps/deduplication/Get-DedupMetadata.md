---
external help file: DedupMetadata.cdxml-help.xml
Module Name: Deduplication
online version: 
schema: 2.0.0
title: Get-DedupMetadata
description: 
keywords: powershell, cmdlet
author: brianlic
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 9B853179-B5D9-4340-B2DC-EE8B75671B22
---

# Get-DedupMetadata

## SYNOPSIS
Returns a DeduplicationMetadata object for every volume that has data deduplication metadata.

## SYNTAX

```
Get-DedupMetadata [[-Volume] <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-DedupMetadata** cmdlet returns a DeduplicationMetadata object for every volume that has optimization metadata.
A DeduplicationMetadata object includes read-only properties describing the nature of the deduplication data store such as chunk counts, container counts, average chunk size, and other statistics.

This cmdlet can some time to run since the entire file system must be scanned.

This cmdlet cannot be part of a schedule; it must be run manually.
If another optimization job is running on the specified volume when you kick of this cmdlet, then this cmdlet will fail.
It will also fail if there is not enough memory for the file system scan and cmdlet processing.
If this happens, then review the events and log files for more information.

To run this cmdlet, you must start Windows PowerShell® with the **Run as administrator** option.

This cmdlet returns the following: 
                       
 - DataChunkCount: Indicates the number of data chunks in a container. 
                       
 - DataContainerCount: Indicates the number of containers in the data store. 
                       
 - DataChunkAverageSize: Indicates the data store size (not including chunk metadata) divided by the total number of data chunks in the data store. 
                       
 - StreamMapCount: Indicates the number of data streams in a container. 
                       
 - StreamMapContainerCount: Indicates the number of containers in the stream map store. 
                       
 - StreamMapAverageChunkCount: Indicates the stream map store size divided by the total number of streams in the store. 
                       
 - HotspotCount: Indicates the number of hotspots in a container. 
                       
 - HotspotContainerCount: Indicates the number of hotspots in the stream map store. 
                       
 - CorruptionCount: Indicates the number of corruptions found on the volume.

## EXAMPLES

### Example 1: Get metadata for a volume
```
PS C:\>Get-DedupMetadata -Volume "D:"
```

This command gets metadata for the D: volume.

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

### -Volume
Specifies one or more file system volumes for which to return a DeduplicationVolumeMetadata object.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Path, Name, DeviceId

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Deduplication/MSFT_DedupVolumeMetadata
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

