---
description: New-ClusterAffinityRule
external help file: ClusterAffinityRule.cdxml-help.xml
Module Name: FailoverClusters
ms.date: 07/27/2023
online version: https://learn.microsoft.com/powershell/module/failoverclusters/new-clusteraffinityrule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-ClusterAffinityRule
---

# New-ClusterAffinityRule

## SYNOPSIS
Creates new affinity rules.

## SYNTAX

```
New-ClusterAffinityRule [-Name] <String> [-RuleType <RuleType>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

This cmdlet allows the creation of new affinity rules for a cluster, which can be used to control
whether certain roles (that is, virtual machines, resource groups, and so on) should run on the
same node. For more information, see
[Cluster affinity](/windows-server/failover-clustering/cluster-affinity).

The available rule types are: the same fault domain, different fault domain, same node, and
different node.

## EXAMPLES

### Example 1 - Create a new affinity rule

```powershell
New-ClusterAffinityRule -Name AffinityRule1 -RuleType SameFaultDomain -Cluster Cluster1
```

This command creates a new affinity rule for `Cluster1` to ensure resources stay within the same
fault domain.

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

### -Name

The name of the rule to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RuleType

The affinity type for the new rule. The valid values for this parameter are:

- `SameFaultDomain` - Resources must stay within the same fault domain.
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

### None

This cmdlet doesn't accept any input from the pipeline.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#root/MSCluster/MSCluster_AffinityRule
The cmdlet returns an object representing an affinity rule as a CIM instance within the
`root/MSCLUSTER/MSCluster_AffinityRule` path.

## NOTES

## RELATED LINKS

[Get-ClusterAffinityRule](Get-ClusterAffinityRule.md)

[Remove-ClusterAffinityRule](Remove-ClusterAffinityRule.md)

[Set-ClusterAffinityRule](Set-ClusterAffinityRule.md)
