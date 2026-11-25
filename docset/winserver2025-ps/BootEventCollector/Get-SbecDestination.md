---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
Module Name: BootEventCollector
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/booteventcollector/get-sbecdestination?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SbecDestination
---

# Get-SbecDestination

## SYNOPSIS
Get destination data files.

## SYNTAX

```
Get-SbecDestination [[-ComputerName] <String[]>] [[-CimSession] <CimSession[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SbecDestination** cmdlet gets the known (per the status log) destination data files.

As the forwarders create the destination files with the data, this information is recorded in the status log, if the status log is enabled.
This information can then be used to present the list of all the known destination data files along with the information of who and when created then.

The status log may contain more than one entry per destination file, if this file has been overwritten more than once and the log has not been compacted since.
However, this function always returns the compacted view, with only one entry per file.
Some of the returned files might not exist any longer if the administrator has deleted them since the time of the last status log compaction.

If the status log is not enabled in the collector configuration, no data is returned.

## EXAMPLES

### Example 1: Get destination files
```
PS C:\> $x = @(Get-SbecDestination)
```

This command gets the destination files, and then stores them in the $x variable.

## PARAMETERS

### -CimSession
Runs the cmdlet on the remote computers through a remote session.
Enter a session object, such as the output of a **New-CimSession** or **Get-CimSession** cmdlet, or an array of these objects.
The default is to run the cmdlet on the local computer.
For more information, see About_CimSession.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the names of the computers on which you want to perform the operation.
You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address for each computer.
For more information see [Invoke-CimMethod](https://go.microsoft.com/fwlink/?LinkId=808801) on MSDN.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None.

## OUTPUTS

### CIM/WMI objects of class \Root\Microsoft\Windows\BootEventCollector\TargetForwardingDestination
The output contains these fields:

- `<TargetEndpoint>`: The target computer's endpoint information in human-readable format, as its host:port string (for example, 127.0.0.1:50000).
- `<TargetMac>`: The target computer's MAC address (if known).
- `<TargetGuid>`: The target computer's SMBIOS GUID (if known).
- `<CollectorEndpoint>`: The host:port information of the endpoint on the collector side.
- `<Computer>`: Target computer name, as determined by the collector according to its configuration.
- `<ForwarderType>`: Type of the forwarder (such as 'etl').
- `<Destination>`: Destination of the data.
The meaning depends on the forwarder type.
A file name (such as for the ETL forwarder), or some other identification.
- `<DestinationPattern>`: Pattern used to generate the destination of the data.
The meaning depends on the forwarder type and configuration.
For a fixed destination, would be the same as the destination itself.
For the destination with rotation of the files would contain the pattern characters that will be replaced with the actual index in the destination.
- `<Error>`: Error message if an error was encountered.
Otherwise will be empty.
- `<ConnectedSince>`: CIM timestamp of when the connection was established.
- `<DisconnectedSince>`: CIM timestamp of when the connection was dropped.
- `<WmiDateTime>`: CIM timestamp of when this state change was recorded.

## NOTES

## RELATED LINKS

[Get-SbecForwarding](./Get-SbecForwarding.md)

[Get-SbecHistory](./Get-SbecHistory.md)

