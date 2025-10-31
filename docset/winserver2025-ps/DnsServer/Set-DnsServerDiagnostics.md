---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerDiagnostics_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/set-dnsserverdiagnostics?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DnsServerDiagnostics
---

# Set-DnsServerDiagnostics

## SYNOPSIS
Sets debugging and logging parameters.

## SYNTAX

### Parameters (Default)
```
Set-DnsServerDiagnostics [-ComputerName <String>] [-PassThru] [-Answers <Boolean>] [-EventLogLevel <UInt32>]
 [-FullPackets <Boolean>] [-IPFilterList <IPAddress[]>] [-LogFilePath <String>] [-MaxMBFileSize <UInt32>]
 [-EnableLoggingForRemoteServerEvent <Boolean>] [-EnableLoggingForPluginDllEvent <Boolean>]
 [-UseSystemEventLog <Boolean>] [-EnableLogFileRollover <Boolean>]
 [-EnableLoggingForZoneLoadingEvent <Boolean>] [-EnableLoggingForLocalLookupEvent <Boolean>]
 [-EnableLoggingToFile <Boolean>] [-EnableLoggingForZoneDataWriteEvent <Boolean>]
 [-EnableLoggingForTombstoneEvent <Boolean>] [-EnableLoggingForRecursiveLookupEvent <Boolean>]
 [-UdpPackets <Boolean>] [-UnmatchedResponse <Boolean>] [-Updates <Boolean>] [-WriteThrough <Boolean>]
 [-SaveLogsToPersistentStorage <Boolean>] [-EnableLoggingForServerStartStopEvent <Boolean>]
 [-Notifications <Boolean>] [-Queries <Boolean>] [-QuestionTransactions <Boolean>] [-ReceivePackets <Boolean>]
 [-SendPackets <Boolean>] [-TcpPackets <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LogLevel
```
Set-DnsServerDiagnostics [-ComputerName <String>] [-PassThru] [-DebugLogging <UInt32>]
 [-OperationLogLevel2 <UInt32>] [-OperationLogLevel1 <UInt32>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### All
```
Set-DnsServerDiagnostics [-ComputerName <String>] [-PassThru] -All <Boolean> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DnsServerDiagnostics** cmdlet sets debugging and logging parameters on a Domain Name System (DNS) server.

To enable debug logging, specify a value of $True for the *FullPackets* parameter and do the following:

- Set the *ReceivePackets* parameter or the *SendPackets* parameter to $True.
- Set the *TcpPackets* parameter or the *UdpPackets* parameter to $True.
- Set the *Notifications* parameter, the *Queries* parameter, or the *Updates* parameter to $True.
- Set the *QuestionTransactions* parameter or the *Answers* parameter to $True.

If you use the *Parameters* parameter set, you must specify at least one of the options in each of the following pairs of parameters:

- **ReceivePackets**, **SendPackets**
- **TcpPackets**, **UdpPackets**
- **Notifications**, **Updates**, **Queries**
- **QuestionTransactions**, **Answers**

The *All* parameter set enables all options except for the following: **LogFilePath**, **MaxMBFileSize**, **EventLogLevel**, **FilterIpAddrList**, **UseSystemEventLog**, and **EnableLogFileRollover**.

Use the *LogLevel* parameter to enable diagnostics at a more detailed level.

## EXAMPLES

### Example 1: Enable diagnostics for outgoing TCP responses for updates
```
PS C:\> Set-DnsServerDiagnostics -SendPackets $True -TcpPackets $True -Answers $True -Updates $True
```

This command enables the diagnostics of outgoing TCP responses for updates.

### Example 2: Enable all diagnostic options except for LogFilePath
```
PS C:\> Set-DnsServerDiagnostics -All $True
```

This command enables all options for DNS server diagnostics except for **LogFilePath**.

### Example 3: Log send packets
```
PS C:\> Set-DnsServerDiagnostics -DebugLogging 0x10000
```

This command logs send packages.

### Example 4: Reset debugging settings
```
PS C:\> Get-DnsServerDiagnostics -ComputerName "DNSServer01" | select -TcpPackets, -UdpPackets | Set-DnsServerDiagnostics -ComputerName "DNSServer02"
```

This command resets the TCP packet debugging and UDP packet debugging options on DNSServer02 to their values on DNSServer01.

## PARAMETERS

### -All
Specifies whether the DNS server logs all events.

```yaml
Type: Boolean
Parameter Sets: All
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Answers
Specifies whether to enable the logging of DNS responses.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -ComputerName
Specifies a DNS server.
The acceptable values for this parameter are: an IPv4 address, an IPv6 address, and any other value that resolves to an IP address, such as fully qualified domain name (FQDN), Hostname, or NETBIOS name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DebugLogging
Specifies the bitmask for debug logging.
Valid values are:

- 0x00000001. The server logs query packet exchanges.
- 0x00000010. The server logs packet exchanges that are related to zone exchanges.
- 0x00000020. The server logs packet exchanges that are related to zone updates.
- 0x00000100. The server logs packets that contain questions.
- 0x00000200. The server logs packets that contain answers.
- 0x00001000. The server logs packets that it sends.
- 0x00002000. The server logs packets that it receives.
- 0x00004000. The server logs User Datagram Protocol (UDP) packet exchanges.
- 0x00008000. The server logs Transmission Control Protocol (TCP) packet exchanges.
- 0x0000FFFF. The server logs operations if you set the following fields to $True: 0x00001000, 0x00002000, 0x00008000, 0x00004000, 0x00000001, 0x00000001, 0x00000020, 0x00000100, and 0x00000200S.
- 0x00010000. Independent of other field values, this bitmap logs Active Directory write operations.
- 0x00020000. Independent of other field values, this bitmap logs Active Directory polling operations and operations that occur during DNS updates (secure and not secure) on Active Directory-integrated zones.
- 0x01000000. If other field values allow it, the server logs the entire packet to the log file.
- 0x02000000. If other field values allow it, the server logs response packets that do not match any outstanding queries.
- 0x80000000. If other field values allow it, the server saves packet logging information to persistent storage.

```yaml
Type: UInt32
Parameter Sets: LogLevel
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableLogFileRollover
Specifies whether to enable log file rollover.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableLoggingForLocalLookupEvent
Specifies whether the DNS server logs local lookup events.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableLoggingForPluginDllEvent
Specifies whether the DNS server logs dynamic link library (DLL) plug-in events.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableLoggingForRecursiveLookupEvent
Specifies whether the DNS server logs recursive lookup events.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableLoggingForRemoteServerEvent
Specifies whether the DNS server logs remote server events.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableLoggingForServerStartStopEvent
Specifies whether the DNS server logs server start and stop events.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableLoggingForTombstoneEvent
Specifies whether the DNS server logs tombstone events.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableLoggingForZoneDataWriteEvent
Specifies Controls whether the DNS server logs zone data write events.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableLoggingForZoneLoadingEvent
Specifies whether the DNS server logs zone load events.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableLoggingToFile
Specifies whether the DNS server logs logging-to-file.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EventLogLevel
Specifies an event log level.
Valid values are:

- 0: No Events
- 1: Errors Only
- 2: Errors and warnings
- 3-7: All Events

```yaml
Type: UInt32
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FullPackets
Specifies whether the DNS server logs full packets.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPFilterList
Specifies an array of IP addresses to filter.
When you enable logging, traffic to and from these IP addresses is logged.
If you do not specify any IP addresses, traffic to and from all IP addresses is logged.

```yaml
Type: IPAddress[]
Parameter Sets: Parameters
Aliases: FilterIPAddressList

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LogFilePath
Specifies a log file path.

```yaml
Type: String
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxMBFileSize
Specifies the maximum size of the log file.
This parameter is relevant if you set **EnableLogFileRollover** and **EnableLoggingToFile** to $True.

```yaml
Type: UInt32
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Notifications
Specifies whether the DNS server logs notifications.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OperationLogLevel1
Specifies a bit flag for the logging level.
Valid values are:

- 0x00000001. The DNS server saves operational logging information to persistent storage.
- 0x00000010. The DNS server logs event logging information to a log file.
- 0x00000020. The DNS server logs operational logging information for server start and stop activities to the log file.
- 0x00002000. The DNS server logs operational logging information for activities that are related to loading a zone from a directory server to the log file.
- 0x00004000. The DNS server logs operational logging information for activities that are related to writing zone data to the directory server to the log file.
- 0x00020000. The DNS server logs operational logging information for activities that are related to updating nodes that have exceeded the tombstone lifetime to the log file.
- 0x00100000. The DNS server logs operational logging information for local resource lookup activities to the log file.
- 0x00200000. The DNS server logs operational logging information for activities that occur during recursive query lookup to the log file.
- 0x00400000. The DNS server logs operational logging information for activities that are related to interaction with remote name servers to the log file.

```yaml
Type: UInt32
Parameter Sets: LogLevel
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OperationLogLevel2
Specifies the additional operations that the DNS server logs.
The default valid value is:

0x01000000.
Valid values for this parameter are: 0x01, 0x02, and 0x03.The DNS server logs operational logging information for activities that are related to interaction with plug-in DLLs to the log file.

```yaml
Type: UInt32
Parameter Sets: LogLevel
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Queries
Specifies whether the DNS server allows query packet exchanges to pass through the content filter, such as the *IPFilterList* parameter.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -QuestionTransactions
Specifies whether the DNS server logs queries.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReceivePackets
Specifies whether the DNS server logs receive packets.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SaveLogsToPersistentStorage
Specifies whether the DNS server saves logs to persistent storage.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SendPackets
Specifies whether the DNS server logs send packets.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TcpPackets
Specifies whether the DNS server logs TCP packets.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -UdpPackets
Specifies whether the DNS server logs UDP packets.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UnmatchedResponse
Specifies whether the DNS server logs unmatched responses.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Updates
Specifies whether the DNS server logs updates.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseSystemEventLog
Specifies whether the DNS server uses the system event log for logging.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WriteThrough
Specifies whether the DNS server logs write-throughs.

```yaml
Type: Boolean
Parameter Sets: Parameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerDiagnostics

## RELATED LINKS

[Get-DnsServerDiagnostics](./Get-DnsServerDiagnostics.md)

