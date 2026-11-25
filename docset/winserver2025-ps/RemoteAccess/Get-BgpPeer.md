---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_BgpPeer_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-bgppeer?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-BgpPeer
---

# Get-BgpPeer

## SYNOPSIS
Gets configuration information for BGP peers.

## SYNTAX

### RoutingDomain
```
Get-BgpPeer [[-Name] <String[]>] [-RoutingDomain <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### AllRoutingDomains
```
Get-BgpPeer [-AllRoutingDomains] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-BgpPeer** cmdlet gets configuration information for Border Gateway Protocol (BGP) peers.
You can specify peers to get by using names or routing domains.

## EXAMPLES

### Example 1: Get configuration information for a peer
```
PS C:\> Get-BgpPeer -Name "TenantSite17"
PeerName            LocalIPAddress      PeerIPAddress       PeerASN             OperationMode       ConnectivityStatus
--------            --------------      -------------       -------             -------------       ------------------
TenantSite17        192.168.1.10        10.1.1.10           64512               Mixed               Connecting
```

This command gets configuration information for the peer named TenantSite17.

### Example 2: Get configuration information for all peers
```
PS C:\> Get-BgpPeer
PeerName            LocalIPAddress      PeerIPAddress       PeerASN             OperationMode       ConnectivityStatus
--------            --------------      -------------       -------             -------------       ------------------
TenantSite17        192.168.1.10        10.1.1.10           64512               Mixed               Connecting
TenantSite22        192.168.1.10        10.1.2.10           64522               Mixed               Connecting
```

This command gets the configuration information for all peers.

### Example 3: View formatted configuration information
```
PS C:\> Get-BgpPeer "TenantSite17" | Format-List
PeerName           : TenantSite17
LocalIPAddress     : 192.168.1.10
PeerIPAddress      : 10.1.1.10
PeerASN            : 64512
OperationMode      : Server
PeeringMode        : Manual
HoldTime(s)        : 180
ConnectivityStatus : Stopped
IngressPolicyList  : {Policy11}
EgressPolicyList   :
MaxAllowedPrefix   :
```

This command gets configuration information for all peers, and then passes them to the Format-List cmdlet by using the pipeline operator.
That cmdlet formats the output to the console.
For more information, type `Get-Help Format-List`.

### Example 4: Get configuration information for all peers in a routing domain
```
PS C:\> Get-BgpPeer -RoutingDomain "Rd001"
PeerName            LocalIPAddress      PeerIPAddress       PeerASN             OperationMode       ConnectivityStatus
--------            --------------      -------------       -------             -------------       ------------------
Tenant46            10.1.1.10           192.168.1.2         64513               Mixed               Connecting
```

This command gets configuration information for all peers of the specified routing domain.
This domain contains only a single peer named Tenant46.

## PARAMETERS

### -AllRoutingDomains
Runs the cmdlet against all routing domains that are setup.

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

### -Name
Specifies an array of names.
The cmdlet gets configuration information for the named peers.

```yaml
Type: String[]
Parameter Sets: RoutingDomain
Aliases: PeerList, PeerId, PeerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RoutingDomain
Specifies the name of the routing domain as a string.
The name is a unique, for the multitenant gateway, user-defined alphanumeric string.

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

### System.String[]

### System.String

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance[]

### Microsoft.Management.Infrastructure.CimInstance#BgpPeerConfig

## NOTES

## RELATED LINKS

[Add-BgpPeer](./Add-BgpPeer.md)

[Remove-BgpPeer](./Remove-BgpPeer.md)

[Set-BgpPeer](./Set-BgpPeer.md)

[Start-BgpPeer](./Start-BgpPeer.md)

[Stop-BgpPeer](./Stop-BgpPeer.md)

