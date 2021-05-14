---
external help file: Test-NetConnection-help.xml
Module Name: NetTCPIP
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/nettcpip/test-netconnection?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
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

## DESCRIPTION
The **Test-NetConnection** cmdlet displays diagnostic information for a connection.
The output includes the results of a DNS lookup, a listing of IP interfaces, an option to test a TCP connection, IPsec rules, and confirmation of connection establishment.

## EXAMPLES

### Example 1: Test a connection
```
PS C:\>Test-NetConnection
ComputerName : gateway.contoso.com 

RemoteAddress : 2620:0:30::197 

InterfaceAlias : Ethernet 3 

SourceAddress : 2001:4898:1b:1046:cda8:e200:e2cd:1e8b 

PingSucceeded : True
```

This command tests a network connection.

### Example 2: Test a connection and display detailed results
```
PS C:\>Test-NetConnection -Port 80 -InformationLevel Detailed
ComputerName : gateway.contoso.com 

RemoteAddress : 2620:0:30::197 

RemotePort : 80 

AllNameResolutionResults : 10.253.21.197 

10.79.197.197 

2620:0:30::197 

MatchingIPsecRules : Ipsec-Win8/Domain-TrafficFromInternet-v6 

NetworkIsolationContext : Internet 

InterfaceAlias : Ethernet 3 

SourceAddress : 2001:4898:1b:1046:cda8:e200:e2cd:1e8b 

NetRoute (NextHop) : fe80::21a:30ff:feaf:5400 

PingSucceeded : True 

PingReplyDetails (RTT) : 1 ms 

TcpTestSucceeded : True
```

This command tests a network connection and sets the **InformationLevel** parameter to Detailed.

### Example 3: Test a connection to a remote host
```
PS C:\>Test-NetConnection -ComputerName www.contoso.com -InformationLevel Detailed
ComputerName : www.contoso.com 

RemoteAddress : 2600:1409::1703:6929 

AllNameResolutionResults : 10.3.105.104 

10.3.105.113 

10.3.105.114 

10.3.105.41 

10.3.105.43 

2600:1409::1703:6929 

2600:1409::1703:692b 

2600:1409::1703:6972 

InterfaceAlias : Ethernet 3 

SourceAddress : 2001:4898:1b:1046:cda8:e200:e2cd:1e8b 

NetRoute (NextHop) : fe80::21a:30ff:feaf:5400 

PingSucceeded : True 

PingReplyDetails (RTT) : 164 ms
```

This command tests a network connection to a remote host named www.contoso.com.

## PARAMETERS

### -CommonTCPPort
Specifies the common service TCP port number.
The acceptable values for this parameter are:

- SMB 
- HTTP 
- RDP
- PING

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
Specifies the Domain Name System (DNS) name or IP address of the target computer that runs the Dynamic Host Configuration Protocol (DHCP) server service.

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

If you set this parameter to Quiet, the cmdlet returns a Boolean value that indicates if the attempt to ping a host or port succeeded.

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
The cmdlet uses this port number to test connectivity to the remote machine.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### none

## OUTPUTS

### NetConnectionResults
Results of the connectivity test to the specified computer name

## NOTES

## RELATED LINKS

