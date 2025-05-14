---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_BgpRoutingPolicyForPeer_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/set-bgproutingpolicyforpeer?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-BgpRoutingPolicyForPeer
---

# Set-BgpRoutingPolicyForPeer

## SYNOPSIS
Modifies BGP routing policies for BGP peers.

## SYNTAX

```
Set-BgpRoutingPolicyForPeer -PolicyName <String[]> [-PeerName <String[]>] [-RoutingDomain <String>]
 -Direction <PolicyDirection> [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-BgpRoutingPolicyForPeer** cmdlet modifies BGP routing policies for BGP peer routers.
Specify the names of the router policies and the direction of the route advertisements to which to add the policies.
The cmdlet clears all the existing routing policies for peers before it applies the new set of policies.
If you do not specify the **PeerName** parameter, the cmdlet adds the router policies that you specify to all BGP peer routers.

## EXAMPLES

### Example 1: Apply router policies to BGP peers
```
PS C:\> Set-BgpRoutingPolicyForPeer -Direction Ingress -PeerName "TenantSite03" -PolicyName "RTPolicy02", "RTPolicy04", "RTPolicy05"



Confirm
BGP peering session could currently be active for TenantSite03. Do you want to apply these policies and restart
corresponding peering sessions?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y
```

This command applies the specified router policies to the Ingress route advertisements of the BGP peer named TenantSite03.
The cmdlet clears all the routing policies that you previously applied to the peers before it applies the new set of policies.
The command prompts the user for confirmation before it applies the router policies.

### Example 2: Apply policies to BGP peers without confirmation
```
PS C:\> Set-BgpRoutingPolicyForPeer -Direction Ingress -PeerName "TenantSite01" -PolicyName "RTPolicy01","RTPolicy02" -Force
```

This command applies the specified router policies to the Ingress route advertisements of the BGP peer named TenantSite01.
The cmdlet clears all the routing policies that you previously applied to the peers before it applies the new set of policies.
Because the command includes the **Force** parameter, it prompts the user for confirmation before it applies the routing policies.

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
Specifies the direction of the route advertisements to which the policies are added.The acceptable values for this parameter are:

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
Aliases: PeerList, PeerId

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

[Add-BgpRoutingPolicyForPeer](./Add-BgpRoutingPolicyForPeer.md)

[Remove-BgpRoutingPolicyForPeer](./Remove-BgpRoutingPolicyForPeer.md)

