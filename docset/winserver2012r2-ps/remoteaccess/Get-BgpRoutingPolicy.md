---
author: Kateyanne
description: 
external help file: PS_BgpRoutingPolicy_v1.0.cdxml-help.xml
manager: jasgro
Module Name: RemoteAccess
ms.author: v-kaunu
ms.date: 12/05/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/remoteaccess/get-bgproutingpolicy?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-BgpRoutingPolicy
---

# Get-BgpRoutingPolicy

## SYNOPSIS
Gets configuration information of BGP routing policies.

## SYNTAX

```
Get-BgpRoutingPolicy [[-Name] <String[]>] [-PolicyType <PolicyType>] [-RoutingDomain <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-BgpRoutingPolicy** cmdlet gets configuration information of BGP routing policies from the policy store.
You can specify the names and policy type of the routing policies to return.
If you do not specify the **Name** and **PolicyType** parameters, the cmdlet returns all routing policies of the local BGP router.

## EXAMPLES

### Example 1: Get BGP routing policies by using a name
```
PS C:\> Get-BgpRoutingPolicy -Name "RTPolicy01", "RTPolicy02", "RTPolicy04", "RTPolicy07"


Get-BgpRoutingPolicy : Policy RTPolicy07 not found.
At line:1 char:1
+ Get-BgpRoutingPolicy RTPolicy01, RTPolicy02, RTPolicy04, RTPolicy07
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : ObjectNotFound: (PS_BgpRoutingPolicy:root/Microsoft/...gpRoutingPolicy) [Get-BgpRoutingP
olicy], CimException
+ FullyQualifiedErrorId : HRESULT 80070490,Get-BgpRoutingPolicy

PolicyName   : RTPolicy04
PolicyType   : ModifyAttribute
MatchClauses : MatchPrefix  : {10.1.4.0/24}
IgnorePrefix : {10.1.4.16/28}
SetClauses   : NewLocalPref : 400

PolicyName   : RTPolicy01
PolicyType   : ModifyAttribute
MatchClauses : MatchASNRange : {64522, 64555}
SetClauses   : NewMED       : 100
AddCommunity : {645:2}

PolicyName   : RTPolicy02
PolicyType   : ModifyAttribute
MatchClauses : MatchASNRange : {64522, 64555}
SetClauses   : NewMED       : 100
AddCommunity : {645:2}
```

This command gets the BGP routing policies named RTPolicy01, RTPolicy02, RTPolicy04, and RTPolicy07.

### Example 2: Get all BGP routing policies
```
PS C:\> Get-BgpRoutingPolicy




PolicyName   : RTPolicy04
PolicyType   : ModifyAttribute
MatchClauses : MatchPrefix  : {10.1.4.0/24}
IgnorePrefix : {10.1.4.16/28}
SetClauses   : NewLocalPref : 400

PolicyName   : RTPolicy05
PolicyType   : ModifyAttribute
MatchClauses : MatchCommunity : {100:500}
SetClauses   : NewMED : 500

PolicyName   : RTPolicy01
PolicyType   : ModifyAttribute
MatchClauses : MatchASNRange : {64522, 64555}
SetClauses   : NewMED       : 100
AddCommunity : {645:2}

PolicyName   : RTPolicy02
PolicyType   : ModifyAttribute
MatchClauses : MatchASNRange : {64522, 64555}
SetClauses   : NewMED       : 100
AddCommunity : {645:2}

PolicyName   : RTPolicy06
PolicyType   : Deny
MatchClauses : MatchASNRange  : {64545, 64555}
MatchCommunity : {100:500}
SetClauses   :
```

This command gets all BGP Routing policies in the policy store.

### Example 3: Get BGP Routing policies by using a policy type
```
PS C:\> Get-BgpRoutingPolicy -PolicyType ModifyAttribute




PolicyName   : RTPolicy04
PolicyType   : ModifyAttribute
MatchClauses : MatchPrefix  : {10.1.4.0/24}
IgnorePrefix : {10.1.4.16/28}
SetClauses   : NewLocalPref : 400

PolicyName   : RTPolicy05
PolicyType   : ModifyAttribute
MatchClauses : MatchCommunity : {100:500}
SetClauses   : NewMED : 500

PolicyName   : RTPolicy01
PolicyType   : ModifyAttribute
MatchClauses : MatchASNRange : {64522, 64555}
SetClauses   : NewMED       : 100
AddCommunity : {645:2}

PolicyName   : RTPolicy02
PolicyType   : ModifyAttribute
MatchClauses : MatchASNRange : {64522, 64555}
SetClauses   : NewMED       : 100
AddCommunity : {645:2}
```

This command gets the BGP Routing policies in the policy store that are a ModifyAttribute type of policy.

### Example 4: Get BGP Routing policies for a Routing Domain
```
PS C:\> Get-BgpRoutingPolicy -RoutingDomain "Rd_001" | ft



PolicyName                    PolicyType                    MatchClauses                  SetClauses
----------                    ----------                    ------------                  ----------
RTPolicy04                    ModifyAttribute               MatchPrefix  : {10.1.4.0/24}  NewLocalPref : 300
IgnorePrefix : {10.1.4.16/28}
```

This command gets all the BGP routing policies in the policy store for the routing domain named Rd_001 in a multi-tenant environment.
The command passes the results of the cmdlet to the **Format-Table** cmdlet by using the pipeline operator.
The **Format-Table** cmdlet formats the output as a table.
For more information, type `Get-Help Format-Table`.

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

### -Name
Specifies an array of names of policies.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: PolicyList, PolicyId, PolicyName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PolicyType
Specifies the type of BGP routing policy.
The acceptable values for this parameter are:

- ModifyAttribute
- Allow
- Deny

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#BgpRoutingPolicyConfig[]

## NOTES

## RELATED LINKS

[Set-BgpRoutingPolicy](./Set-BgpRoutingPolicy.md)

[Add-BgpRoutingPolicy](./Add-BgpRoutingPolicy.md)

[Remove-BgpRoutingPolicy](./Remove-BgpRoutingPolicy.md)

