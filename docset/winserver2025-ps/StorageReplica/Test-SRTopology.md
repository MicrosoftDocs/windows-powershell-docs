---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FileServices.SR.Powershell.dll-Help.xml
Module Name: StorageReplica
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storagereplica/test-srtopology?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-SRTopology
---

# Test-SRTopology

## SYNOPSIS
Validates a potential replication partnership.

## SYNTAX

### DefaultSet
```
Test-SRTopology -SourceComputerName <String> -SourceVolumeName <String[]> -SourceLogVolumeName <String>
 -DestinationComputerName <String> -DestinationVolumeName <String[]> -DestinationLogVolumeName <String>
 -DurationInMinutes <UInt32> -ResultPath <String> [-IgnorePerfTests] [<CommonParameters>]
```

### GenerateReportOnlySet
```
Test-SRTopology [-GenerateReport] -DataPath <String> [<CommonParameters>]
```

## DESCRIPTION
The **Test-SRTopology** cmdlet validates a potential replication partnership.
This cmdlet validate on the local host to the destination computer or remotely between source and destination computers.
To use Windows Server 2016 Nano Server, additional steps are required.
Review Storage Replica documentation on Microsoft TechNet.

This cmdlet performs the following validations:

- SMB can be accessed over the network, which means that TCP port 445 and/or 5445 are open bi-directionally.
- WS-MAN can be accessed over HTTP on the network, which means that TCP port 5985 and 5986 are open.
- SR WMIv2 provider can be accessed and accepts requests.
- The source and destination volumes exist and are writable.
- The source and destination log volume exists with NTFS formatting or ReFS formatting and sufficient free space.
- Storage is initialized in GPT format, not MBR, with matching sector sizes.
- Measures round-trip latency of ICMP and reports the average.
- Measures performance counters for write Input/Output and reports the average seen on that volume.
- Measures estimated initial synchronization time.
- There is sufficient physical memory to run replication.

## EXAMPLES

### Example 1: Validate requirements
```
PS C:\>Test-SRTopology -SourceComputerName "SR-SRV05" -SourceVolumeName "D:" -SourceLogVolumeName "E:" -DestinationComputerName "SR-SRV06" -DestinationVolumeName "D:" -DestinationLogVolumeName "E:" -DurationInMinutes 1 -ResultPath "C:\temp" -IgnorePerfTests
Validating data and log volumes...

Test completed. Result at c:\temp\TestSrTopologyReport-2016-10-11-16-13-43.html
```

This command creates a report that validates the requirements.
It does not check performance.

### Example 2: Validate requirements and performance
```
PS C:\>Test-SRTopology -SourceComputerName "SR-SRV05" -SourceVolumeName "D:" -SourceLogVolumeName "E:" -DestinationComputerName "SR-SRV06" -DestinationVolumeName "D:" -DestinationLogVolumeName "E:" -DurationInMinutes 10 -ResultPath "C:\temp"
Validating data and log volumes...

Measuring Storage Replica recovery and initial synchronization performance...

Measuring Storage Replica synchronous replication performance...

Test completed. Result at c:\temp\TestSrTopologyReport-2016-10-11-16-14-50.html
```

This command creates a report that validates requirements.
The command also measures initial sync and ongoing performance for a total of approximately ten minutes.

### Example 3: Generate a report from previously generated data
```
PS C:\>Test-SRTopology -GenerateReport -DataPath "C:\temp"
Report file c:\temp\files\TestSrTopologyReport-2016-09-22-18-32-48.html now includes data charts
```

This command generates a complete report, which includes charts, from data generated previously on a Nano Server.

## PARAMETERS

### -DataPath
Specifies a path of the raw report files created on  Nano Server with a previous run of this cmdlet.
This parameter is only required to finish generation of reports created on a Nano Server, which do not contain the HTML chart generation controls.
Specify a path of the files created in the *ResultPath* parameter.

```yaml
Type: String
Parameter Sets: GenerateReportOnlySet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationComputerName
Specifies a single replica host computer NetBIOS name or fully qualified domain name (FQDN) for the destination computer.

```yaml
Type: String
Parameter Sets: DefaultSet
Aliases: Destination

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DestinationLogVolumeName
Specifies a drive letter, mount point path, or volume GUID where destination replication logs would be created.
The volume must contain an NTFS-formatted volume or ReFS-formatted volume.
The path must exist.
The path cannot be a mapped drive or UNC path.

```yaml
Type: String
Parameter Sets: DefaultSet
Aliases: DestinationLogVolume

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DestinationVolumeName
Specifies an array of drive letters or mount point paths of the partitions for the replica.
The volume must exist.
The volume cannot be a mapped drive or UNC path.

```yaml
Type: String[]
Parameter Sets: DefaultSet
Aliases: DestinationVolumes

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DurationInMinutes
Specifies the number of minutes to run this cmdlet.
This number is halved for initial sync testing and ongoing replication testing.
This cmdlet creates a 100MB test file during these tests and then removes it at the completion of the tests.

```yaml
Type: UInt32
Parameter Sets: DefaultSet
Aliases: Duration

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GenerateReport
Indicates that this cmdlet converts the raw outputs into a readable HTML file.
This parameter is only required for a Nano Server, which does not contain the HTML chart generation controls.

```yaml
Type: SwitchParameter
Parameter Sets: GenerateReportOnlySet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnorePerfTests
Indicates that this cmdlet only checks requirements.
It does not calculate performance numbers.

```yaml
Type: SwitchParameter
Parameter Sets: DefaultSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResultPath
Specifies the output path for the measurement files and the finished HTML report.

```yaml
Type: String
Parameter Sets: DefaultSet
Aliases: OutputResultPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceComputerName
Specifies a single replica host computer NetBIOS name or FQDN for the source computer.
The default value is uses the local computer.

```yaml
Type: String
Parameter Sets: DefaultSet
Aliases: Source

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceLogVolumeName
Specifies a drive letter, mount point path, or volume GUID where source replication logs would be created.
The volume must contain an NTFS-formatted volume or ReFS-formatted volume.
The path must exist.
The path cannot be a mapped drive or UNC path.

```yaml
Type: String
Parameter Sets: DefaultSet
Aliases: SourceLogVolume

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceVolumeName
Specifies an array of drive letters or mount point paths of the partitions for the replica.
The volume must exist.
The volume cannot be a mapped drive or UNC path.

```yaml
Type: String[]
Parameter Sets: DefaultSet
Aliases: SourceVolumes

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

