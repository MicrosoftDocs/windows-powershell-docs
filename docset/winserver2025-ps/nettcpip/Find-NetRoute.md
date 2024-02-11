---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetRoute.cdxml-help.xml
Module Name: NetTCPIP
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nettcpip/find-netroute?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Find-NetRoute
---

# Find-NetRoute

## SYNOPSIS
Finds the best local IP address and the best route to reach a remote address.

## SYNTAX

```
Find-NetRoute [-InterfaceIndex <UInt32>] [-LocalIPAddress <String>] -RemoteIPAddress <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Find-NetRoute** cmdlet finds the best local IP address and the best route to reach a remote address.
Specify the remote address to reach.
You can also specify an interface and a local address to use to reach the remote address.

For more information about routing, see Chapter 5 - [IP Routing](https://technet.microsoft.com/library/bb727001.aspx) in the TechNet library.

## EXAMPLES

### Example 1: Find a local address and route
```
PS C:\>Find-NetRoute -RemoteIPAddress "10.79.197.200"
IPAddress         : 172.31.234.140
InterfaceIndex    : 3
InterfaceAlias    : Ethernet
AddressFamily     : IPv4
Type              : Unicast
PrefixLength      : 21
PrefixOrigin      : Dhcp
SuffixOrigin      : Dhcp
AddressState      : Preferred
ValidLifetime     : 6.00:10:40
PreferredLifetime : 6.00:10:40
SkipAsSource      : False
PolicyStore       : ActiveStore


Caption            :
Description        :
ElementName        :
InstanceID         : :8:8:8:9:55=55;A<8=;8<=<8;55;
AdminDistance      :
DestinationAddress :
IsStatic           :
RouteMetric        : 0
TypeOfRoute        : 3
AddressFamily      : IPv4
DestinationPrefix  : 0.0.0.0/0
InterfaceAlias     : Ethernet
InterfaceIndex     : 3
NextHop            : 172.31.232.1
PreferredLifetime  : 8.00:00:00
Protocol           : NetMgmt
Publish            : No
Store              : ActiveStore
ValidLifetime      : 8.00:00:00
PSComputerName     :
ifIndex            : 3
```

This command finds a **NetIPAddress** object and **NetRoute** object to use to access the IP address 10.79.197.200.
The command returns two objects.
The first object is the local IP address.
The second object is the local route that includes the selected connectivity path and next hop.

## PARAMETERS

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

### -InterfaceIndex
Specifies an index of a network interface.
The cmdlet finds a route for this interface.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalIPAddress
Specifies a local IP address from which to find a route.
You can specify a host address or a subnet address.
You can also use a wildcard address, such as 0.0.0.0/0 for all IPv4 addresses, ::/0 for all IPv6 addresses, or ANY for all addresses.

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

### -RemoteIPAddress
Specifies a remote IP address to which to find a route.
You can specify a host address or a subnet address.
You can also use a wildcard address, such as 0.0.0.0/0 for all IPv4 addresses, ::/0 for all IPv6 addresses, or ANY for all addresses

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### NetIPAddress, NetRoute

## NOTES

## RELATED LINKS

[Get-NetRoute](./Get-NetRoute.md)

[New-NetRoute](./New-NetRoute.md)

[Remove-NetRoute](./Remove-NetRoute.md)

[Set-NetRoute](./Set-NetRoute.md)

