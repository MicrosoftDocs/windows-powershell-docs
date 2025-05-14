---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
Module Name: BootEventCollector
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/booteventcollector/get-sbecforwarding?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SbecForwarding
---

# Get-SbecForwarding

## SYNOPSIS
Gets the current connections and how data is forwarded.

## SYNTAX

```
Get-SbecForwarding [[-ComputerName] <String[]>] [[-CimSession] <CimSession[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SbecForwarding** cmdlet get the current connections and how data is forwarded from the Setup and Boot Event Collector.
It returns one object for each connection.

## EXAMPLES

### Example 1: Get how data is forwarded
```
PS C:\> $x = @(Get-SbecForwarding)
```

This command gets the forwarding information, and then stores it in the $x variable.

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

### The CIM/WMI objects of class \Root\Microsoft\Windows\BootEventCollector\TargetForwarding.
The objects contain the fields:

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

## NOTES

## RELATED LINKS

[Get-SbecDestination](./Get-SbecDestination.md)

[Get-SbecHistory](./Get-SbecHistory.md)

