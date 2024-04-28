---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_BgpRoutingPolicy_v1.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/add-bgproutingpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-BgpRoutingPolicy
---

# Add-BgpRoutingPolicy

## SYNOPSIS
Adds a BGP routing policy to the policy store.

## SYNTAX

```
Add-BgpRoutingPolicy [-PassThru] [-RoutingDomain <String>] [-IgnorePrefix <String[]>] [-Name] <String>
 [-MatchCommunity <String[]>] [-NewLocalPref <UInt32>] [-AddCommunity <String[]>] [-Force] [-NewMED <UInt32>]
 [-PolicyType] <PolicyType> [-NewNextHop <IPAddress>] [-RemoveCommunity <String[]>] [-MatchPrefix <String[]>]
 [-MatchNextHop <IPAddress[]>] [-MatchASNRange <UInt32[]>] [-ClearMED] [-RemoveAllCommunities]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Add-BgpRoutingPolicy** cmdlet adds a Border Gateway Protocol (BGP) routing policy to the policy store.
The cmdlet selects and configures the routes for the routing policy that match the criteria that you specify for this cmdlet.
If you do not set any matching criteria, you must specify the **Force** parameter to add a BGP routing policy.
You can set the criteria by specifying the following parameters:

- **MatchASNRange**
- **MatchCommunity**
- **MatchNextHop**
- **MatchPrefix**

## EXAMPLES

### Example 1: Add a BGP routing policy that modifies router attributes
```
PS C:\> Add-BgpRoutingPolicy -Name "RTPolicy04" -PolicyType ModifyAttribute -MatchPrefix 10.1.4.0/24 -IgnorePrefix 10.1.4.16/28 -NewLocalPref 400 -PassThru




PolicyName   : RTPolicy04
PolicyType   : ModifyAttribute
MatchClauses : MatchPrefix  : {10.1.4.0/24}
IgnorePrefix : {10.1.4.16/28}
SetClauses   : NewLocalPref : 400
```

This command adds a BGP routing policy named RTPolicy04 to the local BGP router.
The routing policy modifies the **Local-Pref** attribute of the BGP routes that match the value of the **MatchPrefix** parameter.
The command assigns the value of 400 to the **Local-Pref** attribute of the BGP routes that match the network prefix 10.1.4.0/24.
The command specifies that the cmdlet does not modify the **Local-Pref** attribute of the BGP routes that have the network prefix 10.1.4.16/28.

### Example 2: Add a BGP routing policy that disables routes
```
PS C:\> Add-BgpRoutingPolicy -Name RTPolicy06 -PolicyType Deny -MatchASNRange 64545,64555 -PassThru




PolicyName   : RTPolicy06
PolicyType   : Deny
MatchClauses : MatchASNRange : {64545, 64555}
SetClauses   :
```

This command adds a BGP routing policy named RTPolicy06 to the local BGP router.
The routing policy drops the routes that have an ASN in the range of 64545 to 64555 in the **As-Path** attribute from the BGP best path selection process..

### Example 3: Add a BGP routing policy for a routing domain
```
PS C:\> Add-BgpRoutingPolicy -Name RTPolicy01 -RoutingDomain "Rd_001" -PolicyType ModifyAttribute -MatchPrefix 10.1.4.0/24 -IgnorePrefix 10.1.4.16/28 -NewLocalPref 400 -PassThru | Format-Table



PolicyName                    PolicyType                    MatchClauses                  SetClauses
----------                    ----------                    ------------                  ----------
RTPolicy01                    ModifyAttribute               MatchPrefix  : {10.1.4.0/24}  NewLocalPref : 400
IgnorePrefix : {10.1.4.16/28}
```

This command adds a BGP routing policy named RTPolicy01 to the BGP router for the routing domain named Rd_001.
The routing policy sets the value of the **Local-Pref** attribute of the BGP routes that match the value of the **MatchPrefix** parameter.
The command specifies that the cmdlet does not modify the **Local-Pref** attribute of the BGP routes that have the network prefix 10.1.4.16/28.
The command passes the results of the cmdlet to the **Format-Table** cmdlet by using the pipeline operator.
The **Format-Table** cmdlet formats the output as a table.
For more information, type `Get-Help Format-Table`.

## PARAMETERS

### -AddCommunity
Specifies an array of **Community** attribute values.
The routing policy adds the **Community** attribute values to the BGP routes that match the criteria that you specify for  the routing policy.

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
Indicates that the routing policy removes the Multi-Exit Discriminator (MED) value from the route advertisements of the BGP routes that match the criteria that you specify for the routing policy.

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
The cmdlet matches these network addresses in the BGP route advertisements, and it processes the routes that match these criteria.

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
Specifies a name for the routing policy.
The name of a routing policy must be unique.

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
Specifies a new value of the **MED** attribute of the BGP routes that match the criteria that you specify for this cmdlet.

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
Specifies a new IP address value for the **Next-Hop** attribute of the BGP routes that match the criteria that you specify for this cmdlet.

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

Required: True
Position: 2
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

### -RoutingDomain
Specifies the name, as a string, of the routing domain.
The ID of a routing domain is a user-defined alphanumeric string.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.String[]

### System.Nullable`1[[System.UInt32, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.Bgp.PolicyType

### System.Net.IPAddress

### System.Net.IPAddress[]

### System.UInt32[]

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#BgpRoutingPolicyConfig

## NOTES

## RELATED LINKS

[Get-BgpRoutingPolicy](./Get-BgpRoutingPolicy.md)

[Set-BgpRoutingPolicy](./Set-BgpRoutingPolicy.md)

[Remove-BgpRoutingPolicy](./Remove-BgpRoutingPolicy.md)

