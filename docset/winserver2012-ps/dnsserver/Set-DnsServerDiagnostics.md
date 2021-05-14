---
external help file: DnsServer_Cmdlets.xml
Module Name: DnsServer
online version: https://docs.microsoft.com/powershell/module/dnsserver/set-dnsserverdiagnostics?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-DnsServerDiagnostics

## SYNOPSIS
Sets debugging and logging parameters.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-DnsServerDiagnostics [-Answers <Boolean>] [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-EnableLogFileRollover <Boolean>] [-EnableLoggingForLocalLookupEvent <Boolean>]
 [-EnableLoggingForPluginDllEvent <Boolean>] [-EnableLoggingForRecursiveLookupEvent <Boolean>]
 [-EnableLoggingForRemoteServerEvent <Boolean>] [-EnableLoggingForServerStartStopEvent <Boolean>]
 [-EnableLoggingForTombstoneEvent <Boolean>] [-EnableLoggingForZoneDataWriteEvent <Boolean>]
 [-EnableLoggingForZoneLoadingEvent <Boolean>] [-EnableLoggingToFile <Boolean>] [-EventLogLevel <UInt32>]
 [-FullPackets <Boolean>] [-IPFilterList <IPAddress[]>] [-LogFilePath <String>] [-MaxMBFileSize <UInt32>]
 [-Notifications <Boolean>] [-PassThru] [-Queries <Boolean>] [-QuestionTransactions <Boolean>]
 [-ReceivePackets <Boolean>] [-SaveLogsToPersistentStorage <Boolean>] [-SendPackets <Boolean>]
 [-TcpPackets <Boolean>] [-ThrottleLimit <Int32>] [-UdpPackets <Boolean>] [-UnmatchedResponse <Boolean>]
 [-Updates <Boolean>] [-UseSystemEventLog <Boolean>] [-WriteThrough <Boolean>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-DnsServerDiagnostics [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>] [-PassThru]
 [-ThrottleLimit <Int32>] -All <Boolean> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Set-DnsServerDiagnostics [-AsJob] [-CimSession <CimSession[]>] [-ComputerName <String>]
 [-DebugLogging <UInt32>] [-OperationLogLevel1 <UInt32>] [-OperationLogLevel2 <UInt32>] [-PassThru]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-DnsServerDiagnostics** cmdlet sets debugging and logging parameters on a Domain Name System (DNS) server.

If you enable debug logging (set the **FullPackets** parameter to $True), you must satisfy the following conditions:

1. Set the **ReceivePackets** parameter or the **SendPackets** parameter to $True., and:

2. Set the **TcpPackets** parameter or the **UdpPackets** parameter to $True, and:

3. Set the **Notifications** parameter, the **Queries** parameter, or the **Updates** parameter to $True, and:

4. Set the **QuestionTransactions** parameter or the **Answers** parameter to $True.

If you use the first parameter set, you must specify at least one of the options in each of the following entries: 

1. **ReceivePackets**, **SendPackets**

2. **TcpPackets**, **UdpPackets**

3. **Notifications**, **Updates**, **Queries**

4. **QuestionTransactions**, **Answers**

The **All** parameter set enables all options except for the following: **LogFilePath**, **MaxMBFileSize**, **EventLogLevel**, **FilterIpAddrList**, **UseSystemEventLog**, and **EnableLogFileRollover**.

Use the third parameter to enable diagnostics at a more detailed level.

## EXAMPLES

### Example 1: Enable diagnostics for outgoing TCP responses for updates
```
PS C:\>Set-DnsServerDiagnostics -SendPackets $true -TcpPackets $true -Answers $true -Updates $true
```

This command enables the diagnostics of outgoing TCP responses for updates.

### Example 2: Enable all diagnostic options except for LogFilePath
```
PS C:\>Set-DnsServerDiagnostics -All $true
```

This command enables all options for DNS server diagnostics except for **LogFilePath**.

### Example 3: Log send packets
```
PS C:\>Set-DnsServerDiagnostics -DebugLogging 0x10000
```

This command logs send packages.

### Example 4: Reset debugging settings
```
PS C:\>Get-DnsServerDiagnostics -ComputerName "DNSServer01" | select -TcpPackets, -UdpPackets | Set-DnsServerDiagnostics -ComputerName "DNSServer02"
```

This command resets the TCP packet debugging and UDP packet debugging options on DNSServer02 to their values on DNSServer01.

## PARAMETERS

### -All
Controls whether the DNS server logs all events.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Answers
Enables the logging of DNS responses when you set the value to $True.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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
Aliases: 

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
Aliases: 

Required: False
Position: Named
Default value: None
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
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: 0xFFFFFFFF
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableLogFileRollover
Sets a bit flag to enable log file rollover.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableLoggingForLocalLookupEvent
Controls whether the DNS server logs local lookup events.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableLoggingForPluginDllEvent
Controls whether the DNS server logs dynamic link library (DLL) plug-in events.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableLoggingForRecursiveLookupEvent
Controls whether the DNS server logs recursive lookup events.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableLoggingForRemoteServerEvent
Controls whether the DNS server logs remote server events.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableLoggingForServerStartStopEvent
Controls whether the DNS server logs server start and stop events.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableLoggingForTombstoneEvent
Controls whether the DNS server logs tombstone events.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableLoggingForZoneDataWriteEvent
Controls whether the DNS server logs zone data write events.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableLoggingForZoneLoadingEvent
Controls whether the DNS server logs zone load events.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableLoggingToFile
Controls whether the DNS server logs logging-to-file.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EventLogLevel
Specifies an event log level. Valid values are:

- 0: No Events
- 1: Errors Only
- 2: Errors and warnings
- 3-7: All Events

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FullPackets
Controls whether the DNS server logs full packets.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

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
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Notifications
Controls whether the DNS server logs notifications.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OperationLogLevel1
Sets a bit flag for the logging level.
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
Parameter Sets: UNNAMED_PARAMETER_SET_3
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
Parameter Sets: UNNAMED_PARAMETER_SET_3
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
Controls whether the DNS server allows query packet exchanges to pass through the content filter, such as the *IPFilterList* parameter.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -QuestionTransactions
Controls whether the DNS server logs queries.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReceivePackets
Controls whether the DNS server logs receive packets.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SaveLogsToPersistentStorage
Controls whether the DNS server saves logs to persistent storage.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SendPackets
Controls whether the DNS server logs send packets.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TcpPackets
Controls whether the DNS server logs TCP packets.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Controls whether the DNS server logs UDP packets.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UnmatchedResponse
Controls whether the DNS server logs unmatched responses.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Updates
Controls whether the DNS server logs updates.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseSystemEventLog
Controls whether the DNS server uses the system event log for logging.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WriteThrough
Controls whether the DNS server logs write-throughs.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerDiagnostics

## RELATED LINKS

[Get-DnsServerDiagnostics](./Get-DnsServerDiagnostics.md)

