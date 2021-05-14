---
external help file: Failoverv2_Cmdlets.xml
Module Name: FailoverClusters
online version: https://docs.microsoft.com/powershell/module/failoverclusters/set-clusterlog?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-ClusterLog

## SYNOPSIS
Sets the size and level of detail for the cluster log.

## SYNTAX

```
Set-ClusterLog [-Cluster <String>] [-InputObject <PSObject>] [-Level <Int32>] [-Size <Int32>]
```

## DESCRIPTION
The **Set-ClusterLog** cmdlet sets the size and level of detail for the cluster log.
The default level, `3`, includes errors, warnings, and additional information.

## EXAMPLES

### Example 1
```
PS C:\>Set-ClusterLog -Level 1
Name 
---- 
cluster1
```

This example sets the cluster log to a detail level of 1.

### Example 2
```
PS C:\>Set-ClusterLog -Size 1024
Name 
---- 
cluster1
```

This example sets the cluster log size to 1024 MB.

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

### -Level
Specifies the log level to set for the cluster.
The acceptable values for this parameter are:`0` to `5`.

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

### -Size
Specifies the log size to set for the cluster.
The acceptable values for this parameter are:`8` MB to `1024` MB.

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

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## NOTES

## RELATED LINKS

[Get-ClusterLog](./Get-ClusterLog.md)

