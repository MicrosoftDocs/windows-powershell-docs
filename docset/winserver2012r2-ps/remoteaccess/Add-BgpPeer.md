---
author: Kateyanne
description: 
external help file: PS_BgpPeer_v1.0.cdxml-help.xml
manager: jasgro
Module Name: RemoteAccess
ms.author: v-kaunu
ms.date: 12/05/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/remoteaccess/add-bgppeer?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-BgpPeer
---

# Add-BgpPeer

## SYNOPSIS
Adds a BGP peer to the current router.

## SYNTAX

```
Add-BgpPeer [-Name] <String> -LocalIPAddress <IPAddress> -PeerIPAddress <IPAddress> [-LocalASN <UInt32>]
 -PeerASN <UInt32> [-OperationMode <OperationMode>] [-PeeringMode <PeeringMode>] [-HoldTimeSec <UInt16>]
 [-IdleHoldTimeSec <UInt16>] [-MaxAllowedPrefix <UInt32>] [-PassThru] [-RoutingDomain <String>]
 [-Weight <UInt16>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Add-BgpPeer** cmdlet adds a Border Gateway Protocol (BGP) peer to the current router.
Specify the following values for the peer: 

- A name for the peer router
- IP address that the router uses with the peer
- Autonomous system number (ASN) for the peer router

You can also specify the following values: 

- ASN for the local router 
- Maximum number of network prefixes that the local router instance can learn from this peer 
- Preference assigned to routes received from this peer 
- Operation mode and peering mode 
- Hold time, in seconds

Exchange of route information begins when the peering session begins.
If the peering mode is Automatic, the session begins when you add the peer.
If you specify a value of Manual for the **PeeringMode** parameter, use the Start-BgpPeer cmdlet to start the peer session.

## EXAMPLES

### Example 1: Add a peer
```
PS C:\> Add-BgpPeer -Name "TenantSite22" -LocalIPAddress 192.168.1.10 -PeerASN 64512 -PeerIPAddress 10.1.1.10 -PassThru
PeerName            LocalIPAddress      PeerIPAddress       PeerASN             OperationMode       ConnectivityStatus
--------            --------------      -------------       -------             -------------       ------------------
TenantSite22        192.168.1.10        10.1.1.10           64512               Mixed               Connecting
```

This command adds a BGP peer, named TenantSite22, to the router.
The command specifies the IP addresses for the router and the peer, and the peer ASN.
The command selects the default value of Automatic for the peering mode.
The command includes the **PassThru** parameter, so it passes the new object to the console.

### Example 2: Add a peer that uses manual peering mode
```
PS C:\> Add-BgpPeer -Name "TenantSite23" -LocalIPAddress 192.168.1.10 -PeerASN 64512 -PeerIPAddress 10.1.1.10 -OperationMode Server -PassThru -PeeringMode Manual 
PeerName            LocalIPAddress      PeerIPAddress       PeerASN             OperationMode       ConnectivityStatus
--------            --------------      -------------       -------             -------------       ------------------
TenantSite24        192.168.1.10        10.1.1.10           64512               Server              Stopped
```

This command adds a BGP peer, named TenantSite24, to the router.
The command specifies the IP addresses for the router and the peer, and the peer ASN.
The command specifies the **PeeringMode** and **OperationsMode** parameters.
Because the command specifies a value of Manual for the **PeeringMode** parameter, the router drops incoming connections until you start the peering.
The command includes the **PassThru** parameter, so it passes the new object to the console.

### Example 3: Add a peer and specify a routing domain
```
PS C:\> Add-BgpPeer -Name "Tenant19" -LocalIPAddress 10.1.1.10 -PeerASN 64513 -PeerIPAddress 192.168.1.2 -PassThru -RoutingDomain "RD001"
PeerName            LocalIPAddress      PeerIPAddress       PeerASN             OperationMode       ConnectivityStatus
--------            --------------      -------------       -------             -------------       ------------------
Tenant19            10.1.1.10           192.168.1.2         64513               Mixed               Connecting
```

This command adds a BGP peer, named Tenant19, to the router.
The command specifies the IP addresses for the router and the peer, and the peer ASN.
The command also specifies the routing domain as RD001.
The command includes the **PassThru** parameter, so it passes the new object to the console.

## PARAMETERS

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
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HoldTimeSec
Specifies the hold time, in seconds.
If this computer does not receive any messages from the peer within this period, the session expires.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 180
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdleHoldTimeSec
Specifies the time in seconds for which the BGP Peer stays in an idle state after an unsuccessful peer connection attempt.

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
Specifies the ASN for the local router.

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
Specifies the IP address that the local router uses for the peer connection.

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
Specifies the maximum number of network prefixes that this router learns from its peer.

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
Specifies a name.
Provide a unique name for this peer within the routing domain.

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
Specifies the BGP router mode of operation.
The acceptable values for this parameter are:

- Mixed.
The peer both initiates and accepts requests. 
- Server.
The peer only accepts requests. 

The default value is Mixed.

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
Specifies the ASN for the peer.

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
Specifies the IP address of the peer.

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
Specifies the peering mode for the peer.
The acceptable values for this parameter are:

- Automatic.
Starts peering attempts automatically when added. 
- Manual.
Starts peering attempts after you start the session by using the Start-BgpPeer cmdlet. 

The default value is Automatic.

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

### -RoutingDomain
Specifies the name of the routing domain as a string.
The name is a unique, for the multi-tenant gateway, user-defined alphanumeric string.

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

### -Weight
Specifies the preference, as an integer, assigned to routes received from this peer.
Higher values have higher priority.
The default value is 32768.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#BgpPeerConfig

## NOTES

## RELATED LINKS

[Get-BgpPeer](./Get-BgpPeer.md)

[Remove-BgpPeer](./Remove-BgpPeer.md)

[Set-BgpPeer](./Set-BgpPeer.md)

[Start-BgpPeer](./Start-BgpPeer.md)

[Stop-BgpPeer](./Stop-BgpPeer.md)

