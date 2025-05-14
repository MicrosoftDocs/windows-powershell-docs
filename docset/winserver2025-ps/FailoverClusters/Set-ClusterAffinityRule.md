---
description: Set-ClusterAffinityRule
external help file: ClusterAffinityRule.cdxml-help.xml
Module Name: FailoverClusters
ms.date: 07/27/2023
online version: https://learn.microsoft.com/powershell/module/failoverclusters/set-clusteraffinityrule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ClusterAffinityRule
---

# Set-ClusterAffinityRule

## SYNOPSIS
Enable or disable an affinity rule, and update the rule type.

## SYNTAX

### Query (cdxml) (Default)

```
Set-ClusterAffinityRule [[-Name] <String[]>] [-RuleType <RuleType>] [-Enabled <UInt32>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### InputObject (cdxml)

```
Set-ClusterAffinityRule -InputObject <CimInstance[]> [-RuleType <RuleType>] [-Enabled <UInt32>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION

The `Set-ClusterAffinityRule` cmdlet can enable or disable an existing affinity rule. It can also
change the **RuleType**.

## EXAMPLES

### Example 1 - Enable an affinity rule

```powershell
Set-ClusterAffinityRule -Name AffinityRule1 -Enabled $true
```

This example enables the cluster affinity rule named `AffinityRule1`.

### Example 2 - Disable an affinity rule

```powershell
Set-ClusterAffinityRule -Name AffinityRule1 -Enabled $false
```

This example disables the cluster affinity rule named `AffinityRule1`.

### Example 3 - Change an affinity rule type

```powershell
Get-ClusterAffinityRule -Name AffinityRule1 | Set-ClusterAffinityRule -RuleType DifferentNode
```

This example gets the affinity rule named `AffinityRule1` and pipes the affinity rule object to the
`Set-ClusterAffinityRule` cmdlet. The `Set-ClusterAffinityRule` cmdlet changes the affinity rule
type to `DifferentNode`.

## PARAMETERS

### -AsJob

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete.

The cmdlet immediately returns an object that represents the job and then displays the command
prompt. You can continue to work in the session while the job completes. To manage the job, use the
`*-Job` cmdlets. To get the job results, use the
[Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about PowerShell background jobs, see
[about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967)
or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet. The default is the
current session on the local computer.

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

### -Enabled

Enables or disables the affinity rule. The accepted values for this parameter are:

- `0` or `$false`. The affinity rule is disabled.
- `1` or `$true`. The affinity rule is enabled.

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

### -InputObject

Specifies the affinity rule object to change. The value must be an object representing an affinity
rule, like the output that the `Get-ClusterAffinityRule` cmdlet returns.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

The name of the affinity rule to change.

```yaml
Type: String[]
Parameter Sets: Query (cdxml)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Returns the original object passed to the command. By default, this cmdlet doesn't generate any
output.

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

### -RuleType

The affinity type to set the rule to. The valid values for this parameter are:

- `SameFaultDomain` - Resources must stay within the same fault domain.
- `SameNode` - Resources must stay on the same cluster node.
- `DifferentFaultDomain` - Resources must stay in different fault domain (anti-affinity).
- `DifferentNode` - Resources must stay on different cluster nodes (anti-affinity).

```yaml
Type: RuleType
Parameter Sets: (All)
Aliases:
Accepted values: SameFaultDomain, SameNode, DifferentFaultDomain, DifferentNode

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then PowerShell calculates an optimum
throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

When a string is piped to this cmdlet, the value is used as the name of the affinity rule to
change.

### Microsoft.Management.Infrastructure.CimInstance[]

This cmdlet accepts CIM instance objects representing an affinity rule like those returned by the
[Get-ClusterAffinityRule](Get-ClusterAffinityRule.md) cmdlet.

## OUTPUTS

### None

By default, the cmdlet doesn't return any output.

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#root/MSCLUSTER/MSCluster_AffinityRule

When the **PassThru** parameter is specified, the cmdlet returns an object representing an affinity
rule as a CIM instance within the `root/MSCLUSTER/MSCluster_AffinityRule` path.

## NOTES

## RELATED LINKS

[Get-ClusterAffinityRule](Get-ClusterAffinityRule.md)

[New-ClusterAffinityRule](New-ClusterAffinityRule.md)

[Remove-ClusterAffinityRule](Remove-ClusterAffinityRule.md)
