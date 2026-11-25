---
description: Add-ClusterSharedVolumeToAffinityRule
external help file: ClusterAffinityRule.cdxml-help.xml
Module Name: FailoverClusters
ms.date: 07/27/2023
online version: https://learn.microsoft.com/powershell/module/failoverclusters/add-clustersharedvolumetoaffinityrule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-ClusterSharedVolumeToAffinityRule
---

# Add-ClusterSharedVolumeToAffinityRule

## SYNOPSIS
Adds a Cluster Shared Volume (CSV) to an existing affinity rule.

## SYNTAX

### Query (cdxml) (Default)

```
Add-ClusterSharedVolumeToAffinityRule [[-Name] <String[]>] [-ClusterSharedVolumes] <String[]>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### InputObject (cdxml)

```
Add-ClusterSharedVolumeToAffinityRule -InputObject <CimInstance[]>
 [-ClusterSharedVolumes] <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru]
 [<CommonParameters>]
```

## DESCRIPTION

This cmdlet allows you to add cluster shared volumes (CSVs) to an existing affinity rule, using
either the CSV name or object.

## EXAMPLES

### Example 1 - Add a CSV to an affinity rule

```powershell
Add-ClusterSharedVolumeToAffinityRule -ClusterSharedVolumes MyVolume -Name MyRule -Cluster MyCluster
```

This command adds the cluster shared volume _MyVolume_ to the affinity rule _MyRule_ for the cluster
_MyCluster_.

### Example 2 - Add a CSV to an affinity rule using pipeline

```powershell
Get-ClusterAffinityRule -name Rule1 |
 Add-ClusterSharedVolumeToAffinityRule -ClusterSharedVolumes Volume1
```

The command gets the affinity rule `Rule1` object and passes it to the
`Add-ClusterSharedVolumeToAffinityRule` command. The command adds the cluster shared volume
`Volume1` to the affinity rule.

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

### -ClusterSharedVolumes

The cluster shared volumes to add to the affinity rule.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Specifies the affinity rule object that is used in a pipeline command.

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

The name of affinity rule to add cluster shared volumes to.

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

Returns the original affinity rule object passed to the command. By default, this cmdlet doesn't
generate any output.

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

When a string is piped to this cmdlet, the value is used as the name of the affinity rule to add the
cluster shared volume to.

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

[Remove-ClusterSharedVolumeFromAffinityRule](Remove-ClusterSharedVolumeFromAffinityRule.md)
