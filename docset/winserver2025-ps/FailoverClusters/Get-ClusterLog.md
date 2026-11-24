---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/get-clusterlog?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ClusterLog
---

# Get-ClusterLog

## SYNOPSIS
Creates a log file for all nodes, or a specific a node, in a failover cluster.

## SYNTAX

```
Get-ClusterLog [[-Node] <StringCollection>] [-Destination <String>] [-TimeSpan <UInt32>]
 [-UseLocalTime] [-SkipClusterState] [-Health] [-InputObject <PSObject>] [-Cluster <String>]
 [<CommonParameters>]
```

## DESCRIPTION

The `Get-ClusterLog` cmdlet creates a log file for all nodes, or a specific a node, in a failover
cluster.

When creating a log file for the cluster, you can specify the timespan that you want logged
information for in addition to providing a destination for the created logs.

Note: This cmdlet cannot be run remotely without Credential Security Service Provider (CredSSP)
authentication on the server computer.

## EXAMPLES

### Example 1: Create a log file for the local cluster

```powershell
Get-ClusterLog
```

This command creates a log file for the local cluster in the cluster reports folder
`C:\Windows\Cluster\Reports` on each node of the cluster.

### Example 2: Create log files for each node and save them locally

```powershell
Get-ClusterLog -Destination .
```

This command creates a log file for each node of the local cluster, and copies all logs to the local
folder.

### Example 3: Create a log file for the local cluster for previous five minutes

```powershell
Get-ClusterLog -TimeSpan 5
```

This command creates a log file for the local cluster in the cluster reports folder
`C:\Windows\Cluster\Reports` on each node of the cluster. The log covers the last 5 minutes.

## PARAMETERS

### -Cluster

Specifies the name of the cluster on which to run this cmdlet. If the input for this parameter is
`.` or it is omitted, then the cmdlet runs on the local cluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Destination

Specifies the location to which to copy one or more cluster logs. To copy to the current folder, use
`.` for this parameter input. Default location is `C:\Windows\Cluster\Reports`.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Health

Indicates that the cmdlet also logs the health information of the cluster.

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

### -InputObject

Specifies the cluster from which to generate cluster logs.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Node

Specifies the name of the cluster node for which to generate the cluster log.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipClusterState

Indicates that the cmdlet doesn't add additional cluster state information to the cluster logs.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: scs

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeSpan

Specifies the time span in minutes for which to generate the cluster log.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: Span

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseLocalTime

Specifies that the time stamp for each cluster log entry uses local time. By default, the timestamp
uses Greenwich Mean Time (GMT).

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: lt

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

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### System.IO.FileInfo

## NOTES

## RELATED LINKS

[Set-ClusterLog](./Set-ClusterLog.md)
