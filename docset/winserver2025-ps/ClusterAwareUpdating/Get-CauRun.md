---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ClusterAwareUpdating.dll-Help.xml
Module Name: ClusterAwareUpdating
ms.date: 09/27/2022
online version: https://learn.microsoft.com/powershell/module/clusterawareupdating/get-caurun?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CauRun
---

# Get-CauRun

## SYNOPSIS
Gets status information about an updating run currently in progress.

## SYNTAX

### DefaultParamSet (Default)

```
Get-CauRun [[-ClusterName] <String>] [-Credential <PSCredential>] [<CommonParameters>]
```

### WaitForStart

```
Get-CauRun [[-ClusterName] <String>] [-Credential <PSCredential>] [-WaitForStart]
 [<CommonParameters>]
```

### WaitForCompletion

```
Get-CauRun [[-ClusterName] <String>] [-Credential <PSCredential>] [-WaitForCompletion]
 [<CommonParameters>]
```

### ShowClusterNodeState

```
Get-CauRun [[-ClusterName] <String>] [-Credential <PSCredential>] [-ShowClusterNodeState]
 [<CommonParameters>]
```

## DESCRIPTION

The `Get-CauRun` cmdlet gets status information about an updating run currently in progress.
Use this cmdlet to monitor current updating runs.

## EXAMPLES

### Example 1: Get status information about the updating run in progress from the specified cluster

```powershell
Get-CauRun -ClusterName "CONTOSO-FC1"
```

```output
RunId                   : 834dd11e-584b-41f2-8d22-4c9c0471dbad
RunStartTime            : 10/13/2011 1:35:39 PM
CurrentOrchestrator     : NODE1
NodeStatusNotifications : {
Node      : NODE1
Status    : Waiting
Timestamp : 10/13/2011 1:35:49 PM
}
NodeResults             : {
Node                     : NODE2
Status                   : Succeeded
ErrorRecordData          :
NumberOfSucceededUpdates : 0
NumberOfFailedUpdates    : 0
InstallResults           : Microsoft.ClusterAwareUpdating.UpdateInstallResult[]
}
```

This command gets status information about the updating run currently in progress on the cluster
named CONTOSO-FC1.

## PARAMETERS

### -ClusterName

Specifies the name of the cluster for which this cmdlet gets the updating run status. This parameter
is only required when this cmdlet isn't run on a failover cluster node, or this cmdlet is used to
reference a failover cluster different from where the cmdlet is run.

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

### -ShowClusterNodeState

Indicates that this cmdlet gets the status of the Windows Management Instrumentation (WMI) object
that is created on each cluster node. This can be used to debug the status of leftover objects.

```yaml
Type: SwitchParameter
Parameter Sets: ShowClusterNodeState
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WaitForCompletion

Indicates that this cmdlet waits for the updating run to finish. If this parameter is specified, the
cmdlet also writes the updated CAU run objects to the output stream as progress is recorded by the
current CAU Update Coordinator.

```yaml
Type: SwitchParameter
Parameter Sets: WaitForCompletion
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WaitForStart

Indicates that this cmdlet waits for an updating run that is in progress on the specified cluster.
Otherwise the cmdlet waits for an updating run to begin.

```yaml
Type: SwitchParameter
Parameter Sets: WaitForStart
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

### Microsoft.ClusterAwareUpdating.CauRun

### Microsoft.ClusterAwareUpdating.RunState

## NOTES

## RELATED LINKS

[Invoke-CauRun](./Invoke-CauRun.md)

[Stop-CauRun](./Stop-CauRun.md)

