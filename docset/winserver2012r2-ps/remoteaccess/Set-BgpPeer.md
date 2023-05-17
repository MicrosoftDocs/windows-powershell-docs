---
external help file: PS_BgpPeer_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/remoteaccess/set-bgppeer?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-BgpPeer
---

# Set-BgpPeer

## SYNOPSIS
Modifies BGP configuration.

## SYNTAX

```
Set-BgpPeer [-Name] <String> [-LocalIPAddress <IPAddress>] [-PeerIPAddress <IPAddress>] [-LocalASN <UInt32>]
 [-PeerASN <UInt32>] [-OperationMode <OperationMode>] [-PeeringMode <PeeringMode>] [-HoldTimeSec <UInt16>]
 [-IdleHoldTimeSec <UInt16>] [-MaxAllowedPrefix <UInt32>] [-RoutingDomain <String>] [-PassThru] [-Force]
 [-ClearPrefixLimit] [-Weight <UInt16>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-BgpPeer** cmdlet modifies peer configuration for Border Gateway Protocol (BGP) routers.
Specify a peer to modify by using its name.
You can modify the following configuration settings: 

- Autonomous system number (ASN) for the local and peer router instances 
- IP address of the local and peer router instances 
- Maximum number of network prefixes that the local router instance can learn from this peer, or you can remove limit 
- Preference assigned to routes received from this peer 
- Operation mode and peering mode 
- Hold time, in seconds

## EXAMPLES

### Example 1: Change the peering mode to Automatic
```
PS C:\> Set-BgpPeer -Name "TenantSite17" -Force -PeeringMode Automatic -PassThru
PeerName            LocalIPAddress      PeerIPAddress       PeerASN             OperationMode       ConnectivityStatus
--------            --------------      -------------       -------             -------------       ------------------
TenantSite17        192.168.1.10        10.1.1.10           64512               Server              Connecting
```

This command changes the peering mode of the peer named TenantSite17 to Automatic.
The command includes the **PassThru** parameter, so it passes a **BgpPeerConfig** object to the console.
Because the command includes the **Force** parameter, it does not prompt you for confirmation.

### Example 2: Modify settings for a peer
```
PS C:\> Set-BgpPeer -Name "TenantSite17" -OperationMode Mixed -PeeringMode Automatic -PassThru
Confirm
BGP peering session is active for peer RedTenantSite1. Do you want to apply settings and restart peering?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y

PeerName            LocalIPAddress      PeerIPAddress       PeerASN             OperationMode       ConnectivityStatus
--------            --------------      -------------       -------             -------------       ------------------
TenantSite17        192.168.1.10        10.1.1.10           64512               Mixed               Connecting
```

This command modifies the operation mode and the peering mode of the peer named TenantSite17.
The command includes the **PassThru** parameter, so it passes a **BgpPeerConfig** object to the console.
Because the command does not include the **Force** parameter, it prompts you for confirmation.

### Example 3: Modify the ASN of a peer
```
PS C:\> Set-BgpPeer -Name "Tenant17" -PassThru -PeerASN 64515 -RoutingDomain "Rd002" -PassThru 
Confirm
BGP peering session is active for Tenant17 for routing domain Rd002. Do you want to apply settings and restart
peering?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):

PeerName            LocalIPAddress      PeerIPAddress       PeerASN             OperationMode       ConnectivityStatus
--------            --------------      -------------       -------             -------------       ------------------
Tenant17            10.1.1.10           192.168.1.2         64515               Mixed               Connecting
```

This command modifies the ASN of the peer named TenantSite17 in the routing domain Rd002.
The command includes the **PassThru** parameter, so it passes a **BgpPeerConfig** object to the console.
Because the command does not include the **Force** parameter, it prompts you for confirmation.

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

### -ClearPrefixLimit
Indicates that the cmdlet removes the limit on the number of network prefixes learned from the peer.
Specify a limit by using the **MaxAllowedPrefix** parameter.
You cannot specify both the **MaxAllowedPrefix** parameter and the **ClearPrefixLimit** parameter.

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

### -Force
Forces the command to run without asking for user confirmation.

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

### -HoldTimeSec
Specifies the hold time, in seconds.
If this computer does not receive any messages from the peer within this time, the session expires.

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

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxAllowedPrefix
Specifies the maximum number of network prefixes that this router learns from its peer.
To remove this limit, specify the **ClearPrefixLimit** parameter.
You cannot specify both the **MaxAllowedPrefix** parameter and the **ClearPrefixLimit** parameter.

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
The cmdlet modifies settings for the named peer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: PeerId, PeerName

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

Required: False
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

Required: False
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
The name is a unique, for the multitenant gateway, user-defined alphanumeric string.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#BgpPeerConfig

## NOTES

## RELATED LINKS

[Add-BgpPeer](./Add-BgpPeer.md)

[Get-BgpPeer](./Get-BgpPeer.md)

[Remove-BgpPeer](./Remove-BgpPeer.md)

[Start-BgpPeer](./Start-BgpPeer.md)

[Stop-BgpPeer](./Stop-BgpPeer.md)

