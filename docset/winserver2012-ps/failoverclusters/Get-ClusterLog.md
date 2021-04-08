---
author: Kateyanne
external help file: Failoverv2_Cmdlets.xml
manager: dansimp
Module Name: FailoverClusters
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/failoverclusters/get-clusterlog?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-ClusterLog

## SYNOPSIS
Creates a log file for all nodes, or a specific a node, in a failover cluster.

## SYNTAX

```
Get-ClusterLog [[-Node] <StringCollection>] [-Cluster <String>] [-Destination <String>]
 [-InputObject <PSObject>] [-TimeSpan <UInt32>] [-UseLocalTime]
```

## DESCRIPTION
The **Get-ClusterLog** cmdlet creates a log file for all nodes, or a specific a node, in a failover cluster.

When creating a log file for the cluster, you can specify the timespan that you want logged information for in addition to providing a destination for the created logs.

Note: This cmdlet cannot be run remotely without Credential Security Service Provider (CredSSP) authentication on the server computer.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-ClusterLog
Mode                LastWriteTime     Length Name 
----                -------------     ------ ---- 
-a---          9/4/2008   3:53 PM    2211301 Cluster.log 
-a---          9/4/2008   3:53 PM    1261025 Cluster.log
```

This example creates a log file for the local cluster in the cluster reports folder on each node of the cluster.

### EXAMPLE 2
```
PS C:\>Get-ClusterLog -Destination .
Mode                LastWriteTime     Length Name 
----                -------------     ------ ---- 
-a---          9/4/2008   3:55 PM    2211301 node1_cluster.log 
-a---          9/4/2008   3:55 PM    1261025 node2_cluster.log
```

This example creates a log file for each node of the local cluster, and copies all logs to the local folder.

### EXAMPLE 3
```
PS C:\>Get-ClusterLog -TimeSpan 5
Mode                LastWriteTime     Length Name 
----                -------------     ------ ---- 
-a---          9/4/2008   3:58 PM     128299 Cluster.log 
-a---          9/4/2008   4:01 PM     104181 Cluster.log
```

This example creates a log file for the local cluster in the cluster reports folder on each node of the cluster.
The log covers the last 5 minutes.

## PARAMETERS

### -Cluster
Specifies the name of the cluster on which to run this cmdlet.
If the input for this parameter is `.` or it is omitted, then the cmdlet runs on the local cluster.

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
Specifies the location to which to copy one or more cluster logs.
To copy to the current folder, use `.` for this parameter input.

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
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeSpan
Specifies the time span for which to generate the cluster log.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: span

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseLocalTime
Specifies that the time stamp for each cluster log entry uses local time.
By default, the timestamp uses Greenwich Mean Time (GMT).

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

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### System.IO.FileInfo

## NOTES

## RELATED LINKS

[Set-ClusterLog](./Set-ClusterLog.md)

