---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ClusterAwareUpdating.dll-Help.xml
Module Name: ClusterAwareUpdating
ms.date: 09/27/2022
online version: https://learn.microsoft.com/powershell/module/clusterawareupdating/stop-caurun?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-CauRun
---

# Stop-CauRun

## SYNOPSIS
Stops an updating run that is in progress on a cluster.

## SYNTAX

```
Stop-CauRun [[-ClusterName] <String>] [-Credential <PSCredential>] [-Wait] [-Force]
 [<CommonParameters>]
```

## DESCRIPTION

The `Stop-CauRun` cmdlet stops an updating run that is in progress on a failover cluster.

## EXAMPLES

### Example 1: Stop an updating run on the specified cluster

```
Stop-CauRun -ClusterName "CONTOSO-FC1" -Wait -Force
```

This command stops the updating run that is being performed by the CAU Update Coordinator that is
configured on the cluster named CONTOSO-FC1. The cmdlet waits to return until the canceled updating
run has finished. Because the command specifies the **Force** parameter, the cmdlet runs without
displaying confirmation prompts.

## PARAMETERS

### -ClusterName

Specifies the name of the cluster on which to stop an updating run that is in progress. This
parameter is only required when this cmdlet isn't run on a failover cluster node, or this cmdlet is
used to reference a failover cluster different from where the cmdlet is run.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Specifies the administrative credentials for the target cluster.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
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

### -Wait

Indicates that the cmdlet waits until after the canceled updating run has finished. Otherwise,
returns as soon as the stop request has been acknowledged by the current Cluster-Aware Updating
(CAU) Update Coordinator.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS

[Get-CauRun](./Get-CauRun.md)

[Invoke-CauRun](./Invoke-CauRun.md)

