---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_BgpRoutingPolicyForPeer_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/add-bgproutingpolicyforpeer?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-BgpRoutingPolicyForPeer
---

# Add-BgpRoutingPolicyForPeer

## SYNOPSIS
Adds BGP routing policies to BGP peers.

## SYNTAX

```
Add-BgpRoutingPolicyForPeer [-PeerName <String[]>] -PolicyName <String[]> -Direction <PolicyDirection>
 [-RoutingDomain <String>] [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-BgpRoutingPolicyForPeer** cmdlet adds Border Gateway Protocol (BGP) routing policies to BGP peers.
Specify the names of the router policies to add to the BGP peers.
If you do not specify the **PeerName** parameter, the cmdlet adds the router policies that you specify to all BGP peers.

## EXAMPLES

### Example 1: Add a routing policy to a BGP peer
```
PS C:\> Add-BgpRoutingPolicyForPeer -PolicyName "RTPolicy01" -Direction Ingress -PeerName "TenantSite01"



Confirm
BGP peering session could currently be active for TenantSite01. Do you want to apply these policies and restart
corresponding peering sessions?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y
```

This command adds the BGP routing policy named RTPolicy01 to the BGP peer named TenantSite01.
The command specifies the direction of the route advertisement for the BGP peer.

### Example 2: Add a routing policy to a BGP peer in a routing domain
```
PS C:\> Add-BgpRoutingPolicyForPeer -RoutingDomain "Rd_001" -PeerName "TenantSite01" -PolicyName "RoutingPolicy01" -Direction Ingress



Confirm
BGP peering session could currently be active for TenantSite01 for routing domain Rd_001. Do you want to apply these
policies and restart corresponding peering sessions?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):Y
```

This command adds the BGP routing policy named RTPolicy01 to the BGP peer named TenantSite01 for the routing domain named Rd_001.
The command specifies the direction of the route advertisement for the BGP peer.

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

### -Direction
Specifies the direction of the route advertisements to which the policies are added.
The acceptable values for this parameter are:

- Ingress.
The routing policy applies its criteria to incoming route advertisements.
- Egress.
The routing policy applies its criteria to outgoing route advertisements.

```yaml
Type: PolicyDirection
Parameter Sets: (All)
Aliases:
Accepted values: Ingress, Egress

Required: True
Position: Named
Default value: None
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

### -PeerName
Specifies an array of names of BGP peers.
The cmdlet adds the router policies that you specify in the **PolicyName** parameter to the BGP peers.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: PeerId, PeerList

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PolicyName
Specifies an array of names of router policies.
The cmdlet adds these routers to the peers that you specify in the **PeerName** parameter.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: PolicyList, PolicyId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RoutingDomain
Specifies a name, as a string, of a routing domain.
The name of a routing domain is a unique user-defined alphanumeric string.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### System.String

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

[Set-BgpRoutingPolicyForPeer](./Set-BgpRoutingPolicyForPeer.md)

[Remove-BgpRoutingPolicyForPeer](./Remove-BgpRoutingPolicyForPeer.md)

