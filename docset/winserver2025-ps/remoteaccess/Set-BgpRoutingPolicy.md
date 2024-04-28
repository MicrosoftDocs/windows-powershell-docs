---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_BgpRoutingPolicy_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/set-bgproutingpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-BgpRoutingPolicy
---

# Set-BgpRoutingPolicy

## SYNOPSIS
Modifies a routing policy configuration.

## SYNTAX

```
Set-BgpRoutingPolicy [-Name] <String> [-PassThru] [-PolicyType <PolicyType>] [-RoutingDomain <String>] [-Force]
 [-AddCommunity <String[]>] [-RemoveCommunity <String[]>] [-RemovePolicyClause <String[]>]
 [-MatchASNRange <UInt32[]>] [-IgnorePrefix <String[]>] [-MatchCommunity <String[]>] [-MatchPrefix <String[]>]
 [-MatchNextHop <IPAddress[]>] [-NewLocalPref <UInt32>] [-NewMED <UInt32>] [-NewNextHop <IPAddress>]
 [-ClearMED] [-RemoveAllCommunities] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-BgpRoutingPolicy** cmdlet modifies the configuration of a BGP routing policy.
The cmdlet selects and configures the routes for the routing policy that match the criteria that you specify for this cmdlet.
You can set the criteria by specifying the following parameters:

- MatchASNRange
- MatchCommunity
- MatchNextHop
- MatchPrefix

## EXAMPLES

### Example 1: Modify a BGP routing policy
```
PS C:\> Set-BgpRoutingPolicy -Name "RTPolicy01" -PolicyType ModifyAttribute -NewMED 100 -PassThru



Confirm
BGP routing policy RTPolicy01 could currently be active. Do you want to apply these changes and restart corresponding
peerings?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):


PolicyName   : RTPolicy01
PolicyType   : ModifyAttribute
MatchClauses : MatchASNRange : {64522, 64555}
SetClauses   : NewMED       : 100
AddCommunity : {645:2}
```

This command modifies the routing policy named RTPolicy01.
The command sets the ModifyAttribute policy type of the routing policy, and specifies the value 100 for the MED attribute of the BGP routes that match the criteria that you specify for the routing policy.

### Example 2: Modify the community attribute of a BGP routing policy
```
PS C:\> Set-BgpRoutingPolicy -Name "RTPolicy06" -MatchCommunity 100:500 -Force -PassThru





PolicyName   : RTPolicy06
PolicyType   : Deny
MatchClauses : MatchASNRange  : {64545, 64555}
MatchCommunity : {100:500}
SetClauses   :
```

This command modifies the MatchCommunity attribute for the BGP routing policy named RTPolicy06.
Because the cmdlet uses the **Force** parameter, the cmdlet modifies the routing policy without prompting the user for confirmation.

### Example 3: Modify a BGP routing policy of a routing domain
```
PS C:\> Set-BgpRoutingPolicy -Name "RTPolicy04" -RoutingDomain "Rd_001" -NewLocalPref 300 -PassThru



Confirm
BGP routing policy RTPolicy04 could currently be active. Do you want to apply these changes and restart corresponding
peerings for routing domain Rd_001?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):


PolicyName   : RTPolicy04
PolicyType   : ModifyAttribute
MatchClauses : MatchPrefix  : {10.1.4.0/24}
IgnorePrefix : {10.1.4.16/28}
SetClauses   : NewLocalPref : 300
```

This command removes the routing policy named RTPolicy04 from the BGP router for the routing domain named Rd_001.
The command prompts the user for confirmation before it removes the routing policy.

## PARAMETERS

### -AddCommunity
Specifies an array of **Community** attribute values.
The cmdlet adds the **Community** attribute values to the BGP routes that match the criteria that you specify for this cmdlet.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -ClearMED
Indicates that the cmdlet removes the Multi-Exit Discriminator (MED) value from the route advertisements of the BGP routes that match the criteria that you specify for this cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -IgnorePrefix
Specifies an array of network prefixes.
The cmdlet does not process routes that have the network prefix that you specify.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MatchASNRange
Specifies a range of autonomous system numbers (ASNs).
The cmdlet matches these ASNs with the ASNs in the **As-Path** attribute in the BGP route advertisements.
The cmdlet processes the routes that match these criteria.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MatchCommunity
Specifies an array of **Community** attribute values.
The cmdlet matches these **Community** attribute values in the BGP route advertisements.
The cmdlet processes the routes that match these criteria.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MatchNextHop
Specifies an array of **Next-Hop** attribute values.
The cmdlet matches these IP addresses in the BGP route advertisements, and it processes the routes that match these criteria.

```yaml
Type: IPAddress[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MatchPrefix
Specifies an array of network prefixes.
The cmdlet matches these network addresses in the BGP route advertisements and processes the routes that match this criteria.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of a routing policy.

```yaml
Type: String
Parameter Sets: (All)
Aliases: PolicyId, PolicyName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NewLocalPref
Specifies a new value of the **Local-Pref** attribute of the BGP routes that match the criteria that you specify for this cmdlet.

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

### -NewMED
Specifies anew value of the **MED** attribute of the BGP routes that match the criteria that you specify for this cmdlet.

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

### -NewNextHop
Specifies a new IP address value of the **Next-Hop** attribute of the BGP routes that match the criteria that you specify for this cmdlet.

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

### -PolicyType
Specifies the type of BGP routing policy or the filtering action that the cmdlet applies to the BGP routes that match the criteria that you specify for this cmdlet.
The acceptable values for this parameter are:

- ModifyAttribute
- Allow.
The routing policy allows all routes that match the criteria for the BGP best path selection process.
- Deny.
The routing policy filters and drops all routes that match the criteria from the BGP best path selection process.

```yaml
Type: PolicyType
Parameter Sets: (All)
Aliases:
Accepted values: Deny, Allow, ModifyAttribute

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RemoveAllCommunities


```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RemoveCommunity
Specifies an array of **Community** attribute values.
The cmdlet removes the **Community** attribute values from the BGP routes that match the criteria that you specify for this cmdlet.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RemovePolicyClause
Specified an array of policy clauses.
The cmdlet removes these policy clauses from the routing policy.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoutingDomain
Specifies a name, as a string, for a routing domain.
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

### System.String

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.Bgp.PolicyType

### System.String[]

### System.UInt32[]

### System.Net.IPAddress[]

### System.Nullable`1[[System.UInt32, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]

### System.Net.IPAddress

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#BgpRoutingPolicyConfig

## NOTES

## RELATED LINKS

[Get-BgpRoutingPolicy](./Get-BgpRoutingPolicy.md)

[Add-BgpRoutingPolicy](./Add-BgpRoutingPolicy.md)

[Remove-BgpRoutingPolicy](./Remove-BgpRoutingPolicy.md)

