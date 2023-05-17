---
external help file: Failoverv2_Cmdlets.xml
Module Name: FailoverClusters
online version: https://learn.microsoft.com/powershell/module/failoverclusters/set-clusterquorum?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-ClusterQuorum

## SYNOPSIS
Configures quorum options for a failover cluster.

## SYNTAX

```
Set-ClusterQuorum [-Cluster <String>] [-DiskOnly <String>] [-InputObject <PSObject>]
 [-NodeAndDiskMajority <String>] [-NodeAndFileShareMajority <String>] [-NodeMajority]
```

## DESCRIPTION
The **Set-ClusterQuorum** cmdlet configures quorum options for a failover cluster.
The quorum configuration in a failover cluster determines the number of failures that the cluster can sustain.
If an additional failure occurs, the cluster must stop running.
The relevant failures in this context are failures of nodes or, in some cases, of a disk witness (which contains a copy of the cluster configuration) or file share witness.

## EXAMPLES

### Example 1
```
PS C:\>Set-ClusterQuorum -NodeMajority
Cluster                    QuorumResource                  QuorumType 
-------                    --------------                  ---------- 
cluster1                                                 NodeMajority
```

This example changes the quorum configuration to Node Majority on the local cluster.

### Example 2
```
PS C:\>Set-ClusterQuorum -NodeAndDiskMajority "Cluster Disk 7"
Cluster                    QuorumResource                  QuorumType 
-------                    --------------                  ---------- 
cluster1                   Cluster Disk 7         NodeAndDiskMajority
```

This example changes the quorum configuration to Node and Disk Majority on the local cluster, using the disk resource named Cluster Disk 7 for the disk witness.

### Example 3
```
PS C:\>Set-ClusterQuorum -NodeAndFileShareMajority \\fileserver\fsw
Cluster               QuorumResource                       QuorumType 
-------               --------------                       ---------- 
cluster1              File Share Witness     NodeAndFileShareMajority
```

This example changes the quorum configuration to Node and File Share Majority on the local cluster, using the disk resource at \\\\fileserver\fsw for the file share witness.

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

### -DiskOnly
Causes the cluster quorum to be set to disk only type.
This is not recommended as it creates a single point of failure for the cluster.

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
Specifies the cluster on which to change the quorum type.

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

### -NodeAndDiskMajority
Causes the cluster quorum to be set to node and disk majority type.
The name of the disk resource to be used as the disk witness is expected with this parameter.

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

### -NodeAndFileShareMajority
Causes the cluster quorum to be set to node and file share majority type.
The path to the file share to be used as the file share witness is expected with this parameter.

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

### -NodeMajority
Causes the cluster quorum to be set to node majority type.

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

### Microsoft.FailoverClusters.PowerShell.ClusterQuorumSettings

## NOTES

## RELATED LINKS

[Get-ClusterQuorum](./Get-ClusterQuorum.md)

