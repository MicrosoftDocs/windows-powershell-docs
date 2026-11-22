---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 10/21/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/set-clusterquorum?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ClusterQuorum
---

# Set-ClusterQuorum

## SYNOPSIS
Configures quorum options for a failover cluster.

## SYNTAX

```
Set-ClusterQuorum [-DiskOnly <String>] [-NoWitness] [-DiskWitness <String>]
 [-FileShareWitness <String>] [-CloudWitness] [-AccountName <String>] [-Endpoint <String>]
 [-AccessKey <String>] [-InputObject <PSObject>] [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Set-ClusterQuorum` cmdlet configures quorum options for a failover cluster. The quorum
configuration in a failover cluster determines the number of failures that the cluster can sustain.
If an additional failure occurs, the cluster must stop running. The relevant failures in this
context are failures of nodes or, in some cases, of a disk witness (which contains a copy of the
cluster configuration) or file share witness.

## EXAMPLES

### Example 1

```powershell
Set-ClusterQuorum -NodeMajority
```

This example changes the quorum configuration to Node Majority on the local cluster.

### Example 2

```powershell
Set-ClusterQuorum -DiskWitness "Cluster Disk 7"
```

This example changes the quorum configuration to Node and Disk Majority on the local cluster, using
the disk resource named `Cluster Disk 7` for the disk witness.

### Example 3

```powershell
Set-ClusterQuorum -NodeAndFileShareMajority \\fileserver\fsw
```

This example changes the quorum configuration to Node and File Share Majority on the local cluster,
using the disk resource at `\\fileserver\fsw` for the file share witness.

### Example 4

```powershell
$parameters = @{
    CloudWitness = $true
    AccountName  = '<AzureStorageAccountName>'
    AccessKey    = '<AzureStorageAccountAccessKey>'
}
Set-ClusterQuorum @parameters
```

This example changes the quorum configuration to use an Azure Storage Account to use as a Cloud
Witness.

The example uses splatting to pass parameter values from the `$Parameters` variable to the command.
Learn more about [Splatting](/powershell/module/microsoft.powershell.core/about/about_splatting).

## PARAMETERS

### -AccessKey

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

### -AccountName

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

### -CloudWitness

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

### -DiskOnly

Causes the cluster quorum to be set to disk only type. This isn't recommended as it creates a
single point of failure for the cluster.

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

### -DiskWitness

Specifies the name of the disk resource that the cluster quorum uses as the disk witness. Specifying
this parameter sets the cluster quorum to the Node and Disk Majority type.

```yaml
Type: String
Parameter Sets: (All)
Aliases: NodeAndDiskMajority

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Endpoint

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

### -FileShareWitness

Specifies the path of the file share that the cluster quorum uses as the file witness. Specifying
this parameter sets the cluster quorum to the Node and File Share Majority type.

```yaml
Type: String
Parameter Sets: (All)
Aliases: NodeAndFileShareMajority

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

### -NoWitness

Indicates that the cmdlet sets the cluster quorum to the Node Majority type.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: NodeMajority

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

### Microsoft.FailoverClusters.PowerShell.ClusterQuorumSettings

## NOTES

## RELATED LINKS

[Get-ClusterQuorum](./Get-ClusterQuorum.md)
