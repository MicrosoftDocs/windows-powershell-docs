---
description: Remove-ClusterSharedVolumeFromAffinityRule
external help file: ClusterAffinityRule.cdxml-help.xml
Module Name: FailoverClusters
ms.date: 07/28/2023
online version: https://learn.microsoft.com/powershell/module/failoverclusters/remove-clustersharedvolumefromaffinityrule?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ClusterSharedVolumeFromAffinityRule
---

# Remove-ClusterSharedVolumeFromAffinityRule

## SYNOPSIS
Remove a cluster shared volume from an affinity rule.

## SYNTAX

```
Remove-ClusterSharedVolumeFromAffinityRule [[-Name] <String[]>] [-ClusterSharedVolumes] <String[]>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION

## EXAMPLES

```powershell
Remove-ClusterSharedVolumeFromAffinityRule -ClusterSharedVolumes Volume -Name Rule -Cluster Cluster
```

This command removes the cluster shared volume _Volume_ from the affinity rule _Rule_ for the
cluster _Cluster_.

## PARAMETERS

mplete.

The cmdlet immediately returns an object that represents the job and then displays the command
prompt. You can continue to work in the session while the job completes. To manage the job, use the
`*-Job` cmdlets. To get the job results, use the
[Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see
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

uns the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
r [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet. The default is the
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

he clustered shared volumes that should be added to the given affinity rule

ype: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

pecifies the input object that is used in a pipeline command.

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

he name of the affinity rule to add groups to.

```yaml
Type: String[]
Parameter Sets: Query (cdxml)
Aliases: Set

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

Returns an object representing the item with which you are working. By default, this cmdlet doesn't
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

pecifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell&reg; calculates an
optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the
computer. The throttle limit applies only to the current cmdlet, not to the session or to the
computer.

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

his cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#root/MSCLUSTER/MSCluster_AffinityRule

## NOTES

## RELATED LINKS
