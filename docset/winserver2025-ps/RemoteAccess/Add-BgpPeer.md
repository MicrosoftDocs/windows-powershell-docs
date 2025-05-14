---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_BgpPeer_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/add-bgppeer?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-BgpPeer
---

# Add-BgpPeer

## SYNOPSIS
Adds a new BGP peer.

## SYNTAX

```
Add-BgpPeer [-Name] <String> -LocalIPAddress <IPAddress> -PeerIPAddress <IPAddress> [-LocalASN <UInt32>]
 -PeerASN <UInt32> [-OperationMode <OperationMode>] [-PeeringMode <PeeringMode>] [-HoldTimeSec <UInt16>]
 [-IdleHoldTimeSec <UInt16>] [-MaxAllowedPrefix <UInt32>] [-PassThru] [-RoutingDomain <String>]
 [-Weight <UInt16>] [-RouteReflectorClient <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Add-BgpPeer** cmdlet adds a new peer to the Border Gateway Protocol (BGP router).
This cmdlet returns error information if errors occur while adding the peer configuration.

## EXAMPLES

### Example 1: Add a BGP peer to the BGP router and establish a session
```
PS C:\>Add-BgpPeer -Name "RedTenantSite1" -LocalIPAddress 192.168.1.10 -PeerIPAddress 14.1.1.10 -PeerASN 64512 -PassThru

PeerName            LocalIPAddress      PeerIPAddress       PeerASN             OperationMode       ConnectivityStatus
--------            --------------      -------------       -------             -------------       ------------------
RedTenantSite1      192.168.1.10        14.1.1.10           64512               Mixed               Connecting
```

This command adds a BGP peer to the BGP router and automatically starts establishing BGP peering session with that neighbor.

### Example 2: Add a BGP peer to a BGP router that will listen for incoming connections
```
PS C:\>Add-BgpPeer -Name "RedTenantSite1" -LocalIPAddress 192.168.1.10 -PeerIPAddress 14.1.1.10 -PeerASN 64512  -OperationMode Server -PeeringMode Manual -PassThru
PeerName            LocalIPAddress      PeerIPAddress       PeerASN             OperationMode       ConnectivityStatus
--------            --------------      -------------       -------             -------------       ------------------
RedTenantSite1      192.168.1.10        14.1.1.10           64512               Server              Stopped
```

This command adds a new BGP Peer to the BGP router which will listen for incoming connections from neighbor.
PeeringMode is set to Manual, so unless this peering is started manually, the incoming connections requests will be dropped.

### Example 3: Add a BGP peer to a BGP router of a specified routing domain
```
PS C:\>Add-BgpPeer -RoutingDomain Rd_001 -Name BlueTenant1 -LocalIPAddress 14.1.1.10 -PeerIPAddress 192.168.1.2 -PeerASN 64513 -PassThru
PeerName            LocalIPAddress      PeerIPAddress       PeerASN             OperationMode       ConnectivityStatus
--------            --------------      -------------       -------             -------------       ------------------
BlueTenant1         14.1.1.10           192.168.1.2         64513               Mixed               Connecting
```

This command adds a new BGP Peer to the BGP Router of the specified routing domain in Multi-tenant environment and automatically starts establishing BGP peering session.

### Example 4: Add a Route Reflector client BGP peer to a BGP router
```
PS C:\>Add-BgpPeer -Name RRClient1 -LocalIPAddress 14.1.1.10 -PeerIPAddress 192.168.1.2 -PeerASN 64513 -PassThru -RouteReflectorClient $true
PeerName            LocalIPAddress      PeerIPAddress       PeerASN             OperationMode       ConnectivityStatus
--------            --------------      -------------       -------             -------------       ------------------
RRClient1           14.1.1.10           192.168.1.2         64513               Mixed               Connected
```

This command adds a new Route Reflector client BGP Peer to the BGP Router and automatically starts establishing BGP peering session.

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

### -HoldTimeSec
Specifies the configured value of HoldTime in seconds after the BGP session expires if no BGP message is received.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdleHoldTimeSec
Specifies the configured value of IdleHoldTime in seconds after the BGP Session expires if no BGP message is received.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LocalASN
Specifies the local autonomous systems (AS) number of the BGP router instance for this peer.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LocalIPAddress
Specifies the local BGP Router's peering IP Address.
It can be IPv4 or IPv6 address type.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxAllowedPrefix
Specifies the maximum number of allowed IPv4 or IPv6 network prefixes that can be learned from the given neighbor.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the unique name for the peering with specified BGP neighbor.

```yaml
Type: String
Parameter Sets: (All)
Aliases: PeerName, PeerId

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OperationMode
Specifies the BGP Router's mode of operation.
Operating modes include:

- Peering Initiator as well as peering acceptor
- Only acting as a passive peering request acceptor.

```yaml
Type: OperationMode
Parameter Sets: (All)
Aliases:
Accepted values: Mixed, Server

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

### -PeerASN
Specifies the neighbor BGP Router's AS Number.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PeerIPAddress
Specifies the neighbor BGP router's peering IP address.
It can be of IPv4 or IPv6 address type.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PeeringMode
Specifies the parameter to configure peering mode for the given peer.

```yaml
Type: PeeringMode
Parameter Sets: (All)
Aliases:
Accepted values: Automatic, Manual

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RouteReflectorClient
Specifies whether the current peer is a Route Reflector client peer or non-client peer.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RoutingDomain
Specifies the user-defined unique alphanumeric identifier for the routing domain.

```yaml
Type: String
Parameter Sets: (All)
Aliases: RoutingDomainName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent connections that can be established to run this command.
If you omit this parameter or enter a value of 0, the default value, 32, is used.
The throttle limit applies only to the current command, not to the session or to the computer.

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

### -Weight
Specifies administrative preference assigned to the routes received from this peer.

```yaml
Type: UInt16
Parameter Sets: (All)
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

### System.String

### System.Net.IPAddress

### System.Nullable`1[[System.UInt32, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]

### System.UInt32

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.Bgp.OperationMode

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.Bgp.PeeringMode

### System.UInt16

### System.Nullable`1[[System.Boolean, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#BgpPeerConfig

## NOTES

## RELATED LINKS

[Get-BgpPeer](./Get-BgpPeer.md)

[Remove-BgpPeer](./Remove-BgpPeer.md)

[Set-BgpPeer](./Set-BgpPeer.md)

[Start-BgpPeer](./Start-BgpPeer.md)

[Stop-BgpPeer](./Stop-BgpPeer.md)

