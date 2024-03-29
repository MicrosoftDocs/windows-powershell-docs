---
external help file: Failoverv2_Cmdlets.xml
Module Name: FailoverClusters
online version: https://learn.microsoft.com/powershell/module/failoverclusters/get-clustercheckpoint?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-ClusterCheckpoint

## SYNOPSIS
Retrieves a cryptographic key checkpoint or registry checkpoint for a resource.

## SYNTAX

```
Get-ClusterCheckpoint [[-ResourceName] <StringCollection>] [-CheckpointName <String>] [-Cluster <String>]
 [-CryptoCheckpoint] [-InputObject <PSObject>] [-RegistryCheckpoint]
```

## DESCRIPTION
The **Get-ClusterCheckpoint** cmdlet retrieves a cryptographic key checkpoint or registry checkpoint for a resource.

Checkpoints help provide failover support for applications that store configuration information locally instead of or in addition to storing information in the cluster configuration database.
Applications might store information locally in two ways.
One way is to store configuration information in the registry on the local server; another way is to use cryptographic keys on the local server.

## EXAMPLES

### Example 1
```
PS C:\>Get-ClusterCheckpoint
Resource                      Name                          Type                          Key 
--------                      ----                          ----                          --- 
Cluster Name                  Microsoft Enhanced Cryptog...                               b5a571f2-c28b-48fa-b82f-a8... 
Cluster Name                  software\clusname
```

This example retrieves all cluster checkpoints.

### Example 2
```
PS C:\>Get-ClusterResource -ResourceName "Cluster Name" | Get-ClusterCheckpoint -CryptoCheckpoint
Resource                      Name                          Type                          Key 
--------                      ----                          ----                          --- 
Cluster Name                  Microsoft Enhanced Cryptog...                               b5a571f2-c28b-48fa-b82f-a8...
```

This example retrieves the cryptographic checkpoints for the resource named Cluster Name.

## PARAMETERS

### -CheckpointName
Specifies the name of checkpoints for which to search.
Use of wildcard expressions is accepted.

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

### -CryptoCheckpoint
Specifies that cryptographic checkpoints will be retrieved.

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
Specifies the cluster on which to run the cmdlet or the cluster resource for which to retrieve the checkpoint.

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

### -RegistryCheckpoint
Specifies that registry checkpoints will be retrieved.

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

### -ResourceName
Specifies the resource for which to retrieve the checkpoint.

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

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Add-ClusterCheckpoint](./Add-ClusterCheckpoint.md)

[Remove-ClusterCheckpoint](./Remove-ClusterCheckpoint.md)

