---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_BgpStatistics_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-bgpstatistics?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-BgpStatistics
---

# Get-BgpStatistics

## SYNOPSIS
Retrieves BGP peering-related message and route advertisement statistics.

## SYNTAX

### RoutingDomain
```
Get-BgpStatistics [-RoutingDomain <String>] [-PeerName <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### AllRoutingDomains
```
Get-BgpStatistics [-AllRoutingDomains] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-BgpStatistics** cmdlet retrieves Border Gateway Protocol (BGP) peering-related message and route advertisement statistics.

## EXAMPLES

### Example 1: Retrieve all BPG message and route statistics
```
PS C:\> Get-BgpStatistics




PeerName                 : Tenant-01
TcpConnectionEstablished : 14-03-2013 02:57:04
TcpConnectionClosed      : 14-03-2013 02:56:34
OpenMessage:
          LastSent                 : 14-03-2013 02:57:04
          LastReceived             : 14-03-2013 02:57:04
          SentCount                : 4
          ReceivedCount            : 4
UpdateMessage:
          LastSent                 : 14-03-2013 02:57:04
          LastReceived             : 14-03-2013 02:57:04
          SentCount                : 4
          ReceivedCount            : 4
NotificationMessage:
          LastSent                 : 01-01-0001 00:00:00
          LastReceived             : 13-03-2013 08:24:46
          SentCount                : 0
          ReceivedCount            : 2
KeepAliveMessage:
          LastSent                 : 14-03-2013 03:00:31
          LastReceived             : 14-03-2013 03:00:32
          SentCount                : 1277
          ReceivedCount            : 1273
RouteRefreshMessage:
          LastSent                 : 01-01-0001 00:00:00
          LastReceived             : 01-01-0001 00:00:00
          SentCount                : 0
          ReceivedCount            : 0
IPv4Route:
          UpdateSentCount          : 4
          UpdateReceivedCount      : 4
          WithdrawalSentCount      : 0
          WithdrawalReceivedCount  : 0
IPv6Route:
          UpdateSentCount          : 0
          UpdateReceivedCount      : 0
          WithdrawalSentCount      : 0
          WithdrawalReceivedCount  : 0
```

This command retrieves the BGP message and route statistics.

### Example 2: Retrieve BGP message and route statistics for a routing domain
```
PS C:\> Get-BgpStatistics -RoutingDomain Rd_02
PeerName                 : Tenant-01
TcpConnectionEstablished : 14-03-2013 02:57:04
TcpConnectionClosed      : 14-03-2013 02:56:34
OpenMessage:
          LastSent      : 14-03-2013 02:57:04
          LastReceived  : 14-03-2013 02:57:04
          SentCount     : 4
          ReceivedCount : 4
UpdateMessage:
          LastSent      : 14-03-2013 02:57:04
          LastReceived  : 14-03-2013 02:57:04
          SentCount     : 4
          ReceivedCount : 4
NotificationMessage:
          LastSent      : 01-01-0001 00:00:00
          LastReceived  : 13-03-2013 08:24:46
          SentCount     : 0
          ReceivedCount : 2
KeepAliveMessage:
          LastSent      : 14-03-2013 03:00:31
          LastReceived  : 14-03-2013 03:00:32
          SentCount     : 1277
          ReceivedCount : 1273
RouteRefreshMessage:
          LastSent      : 01-01-0001 00:00:00
          LastReceived  : 01-01-0001 00:00:00
          SentCount     : 0
          ReceivedCount : 0
IPv4Route:
          UpdateSentCount         : 4
          UpdateReceivedCount     : 4
          WithdrawalSentCount     : 0
          WithdrawalReceivedCount : 0
IPv6Route:
          UpdateSentCount         : 0
          UpdateReceivedCount     : 0
          WithdrawalSentCount     : 0
          WithdrawalReceivedCount : 0
```

This command retrieves the BGP message and route statistics for a routing domain named Rd_02.

## PARAMETERS

### -AllRoutingDomains
Use this command to retrieve details about all routing domains.

```yaml
Type: SwitchParameter
Parameter Sets: AllRoutingDomains
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -PeerName
Specifies an array of peer names for which to retrieve the BGP message and route statistics.

```yaml
Type: String[]
Parameter Sets: RoutingDomain
Aliases: PeerId, PeerList

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RoutingDomain
Specifies an ID, as a string, for a routing domain.
The ID of a routing domain is a unique user-defined alphanumeric string.

```yaml
Type: String
Parameter Sets: RoutingDomain
Aliases: RoutingDomainName

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.String[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance[]

### Microsoft.Management.Infrastructure.CimInstance#BgpStatistics

## NOTES

## RELATED LINKS

