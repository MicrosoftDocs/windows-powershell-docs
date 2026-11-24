---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Test-NetConnection-help.xml
Module Name: NetTCPIP
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nettcpip/test-netconnection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-NetConnection
---

# Test-NetConnection

## SYNOPSIS
Displays diagnostic information for a connection.

## SYNTAX

### ICMP
```
Test-NetConnection [[-ComputerName] <String>] [-TraceRoute] [-Hops <Int32>] [-InformationLevel <String>]
 [<CommonParameters>]
```

### CommonTCPPort
```
Test-NetConnection [[-ComputerName] <String>] [-CommonTCPPort] <String> [-InformationLevel <String>]
 [<CommonParameters>]
```

### RemotePort
```
Test-NetConnection [[-ComputerName] <String>] -Port <Int32> [-InformationLevel <String>] [<CommonParameters>]
```

### NetRouteDiagnostics
```
Test-NetConnection [[-ComputerName] <String>] [-DiagnoseRouting] [-ConstrainSourceAddress <String>]
 [-ConstrainInterface <UInt32>] [-InformationLevel <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Test-NetConnection** cmdlet displays diagnostic information for a connection.
It supports ping test, TCP test, route tracing, and route selection diagnostics.
Depending on the input parameters, the output can include the DNS lookup results, a list of IP interfaces, IPsec rules, route/source address selection results, and/or confirmation of connection establishment.

## EXAMPLES

### Example 1: Test ping connectivity
```
PS C:\> Test-NetConnection
ComputerName           : internetbeacon.msedge.net

RemoteAddress          : 2a01:111:2003::52

InterfaceAlias         : Ethernet

SourceAddress          : 2001:4898:d8:33:81e8:7b49:8bf5:8710

PingSucceeded          : True

PingReplyDetails (RTT) : 5 ms
```

This command tests ping connectivity to a default server.

### Example 2: Test ping connectivity with detailed results
```
PS C:\> Test-NetConnection -InformationLevel "Detailed"
ComputerName           : internetbeacon.msedge.net

RemoteAddress          : 2a01:111:2003::52

NameResolutionResults  : 2a01:111:2003::52

                         13.107.4.52

InterfaceAlias         : Ethernet

SourceAddress          : 2001:4898:d8:33:81e8:7b49:8bf5:8710

NetRoute (NextHop)     : fe80::200:5eff:fe00:203

PingSucceeded          : True

PingReplyDetails (RTT) : 6 ms
```

This command tests ping connectivity to a default server and sets the *InformationLevel* parameter to Detailed.

### Example 3: Test TCP connectivity and display detailed results
```
PS C:\> Test-NetConnection -Port 80 -InformationLevel "Detailed"
ComputerName            : internetbeacon.msedge.net

RemoteAddress           : 2a01:111:2003::52

RemotePort              : 80

NameResolutionResults   : 2a01:111:2003::52

                          13.107.4.52

MatchingIPsecRules      : Ipsec/Domain-TrafficFromInternet-v6

NetworkIsolationContext : Internet

IsAdmin                 : False

InterfaceAlias          : Ethernet

SourceAddress           : 2001:4898:d8:33:81e8:7b49:8bf5:8710

NetRoute (NextHop)      : fe80::200:5eff:fe00:203

TcpTestSucceeded        : True
```

This command tests TCP connectivity to a default server and sets the *InformationLevel* parameter to Detailed.

### Example 4: Test a connection to a remote host
```
PS C:\> Test-NetConnection -ComputerName "www.contoso.com" -InformationLevel "Detailed"
PingReplyDetails (RTT) : 164 ms

ComputerName           : www.contoso.com

RemoteAddress          : 65.55.39.10

NameResolutionResults  : 65.55.39.10

                         64.4.6.100

InterfaceAlias         : Ethernet

SourceAddress          : 10.137.193.122

NetRoute (NextHop)     : 10.137.192.1

PingSucceeded          : True

PingReplyDetails (RTT) : 164 ms
```

This command tests ping connectivity to a remote host named www.contoso.com.

### Example 5: Perform route diagnostics to connect to a remote host
```
PS C:\> Test-NetConnection -ComputerName www.contoso.com -DiagnoseRouting -InformationLevel Detailed
ComputerName : www.contoso.com

RemoteAddress : 2001:428:3805:187::2768

SelectedSourceAddress : 2001:4898:e0:79:f17c:d212:8743:43c2

OutgoingInterfaceIndex : 4

SelectedNetRoute : DestinationPrefix: ::/0 NextHop: fe80::200:5eff:fe00:202

RouteSelectionEvents : IP: Route [DestinationPrefix: ::/0 NextHop: fe80::200:5eff:fe00:202 InterfaceIndex: 4 InterfaceMetric: 10 RouteMetric: 256] is preferred over

Route [DestinationPrefix: ::/0 NextHop: fe80::200:5eff:fe00:202 InterfaceIndex: 5 InterfaceMetric: 10 RouteMetric: 256] for
Destination: 2001:428:3805:187::2768 in Compartment: 1, Reason: RouteOrder.

SourceAddressSelectionEvents : IP: Source address 2001:4898:e0:79:f17c:d212:8743:43c2 is preferred over fe80::f17c:d212:8743:43c2 for destination 2001:428:3805:187::2768 Rule = 2.0.

RouteDiagnosticsSucceeded : True
```

This command performs route diagnostics to reach a remote host named www.contoso.com.

### Example 6: Perform route diagnostics to connect to a remote host with routing constraints
```
PS C:\> Test-NetConnection -ComputerName "www.contoso.com" -ConstrainInterface 5 -DiagnoseRouting -InformationLevel "Detailed"
ComputerName : www.contoso.com

RemoteAddress : 2600:1409:a:185::2768

ConstrainInterfaceIndex : 5

SelectedSourceAddress : 2001:4898:e0:79:75dd:64cf:d9ff:f86

OutgoingInterfaceIndex : 5

SelectedNetRoute : DestinationPrefix: ::/0

NextHop: fe80::200:5eff:fe00:202

RouteSelectionEvents : IP: Route [DestinationPrefix: ::/0 NextHop: fe80::200:5eff:fe00:202 InterfaceIndex: 4

RouteMetric: 256] is blocked for Destination: 2600:1409:a:185::2768 ConstrainInterfaceIndex: 5 ConstrainScopeZone: 1 in Compartment: 1, Reason: InterfaceConstraint.

SourceAddressSelectionEvents : IP: Source address 2001:4898:e0:79:75dd:64cf:d9ff:f86 is preferred over fe80::75dd:64cf:d9ff:f86 for destination 2600:1409:a:185::2768 Rule = 2.0.

IP: Source address 2001:4898:e0:79:75dd:64cf:d9ff:f86 is preferred over fe80::75dd:64cf:d9ff:f86 for destination 2600:1409:a:185::2768 Rule = 2.0.

RouteDiagnosticsSucceeded : True
```

This command performs route diagnostics to reach a remote host named www.contoso.com with routing constraints.

## PARAMETERS

### -CommonTCPPort
Specifies the common service TCP port number.
The acceptable values for this parameter are:

- SMB
- HTTP
- RDP
- WINRM

```yaml
Type: String
Parameter Sets: CommonTCPPort
Aliases:
Accepted values: HTTP, RDP, SMB, WINRM

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the Domain Name System (DNS) name or IP address of the target computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: RemoteAddress, cn

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ConstrainInterface
Specifies the interface constraint to use for route diagnostics.

```yaml
Type: UInt32
Parameter Sets: NetRouteDiagnostics
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConstrainSourceAddress
Specifies the source address constraint to use for route diagnostics.

```yaml
Type: String
Parameter Sets: NetRouteDiagnostics
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiagnoseRouting
Indicates that route diagnostics runs to output the route and source address selection information for the remote host.

```yaml
Type: SwitchParameter
Parameter Sets: NetRouteDiagnostics
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Hops
Specifies the number of hops to traverse in a trace route command.

```yaml
Type: Int32
Parameter Sets: ICMP
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationLevel
Specifies the information level.
The acceptable values for this parameter are:

- Detailed
- Quiet

If you set this parameter to Quiet, the cmdlet returns basic information.
For example, for a ping test, this cmdlet returns a Boolean value that indicates whether the attempt to ping a host or port is successful.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Quiet, Detailed

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port
Specifies the TCP port number on the remote computer.
The cmdlet uses this port number to test connectivity to the remote computer.

```yaml
Type: Int32
Parameter Sets: RemotePort
Aliases: RemotePort

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TraceRoute
Indicates that Tracert runs to test connectivity to the remote host.

```yaml
Type: SwitchParameter
Parameter Sets: ICMP
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

### None

## OUTPUTS

### NetRouteDiagnostics
This object displays route diagnostics information and is returned if you specify the NetRouteDiagnostics parameter set.

### NetConnectionResults
This object displays connection results and is returned if you specify the CommonTCPPort, RemotePort, or ICMP parameter set.

## NOTES

## RELATED LINKS

