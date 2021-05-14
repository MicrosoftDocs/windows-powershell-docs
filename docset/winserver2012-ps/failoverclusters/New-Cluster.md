---
external help file: Failoverv2_Cmdlets.xml
Module Name: FailoverClusters
online version: https://docs.microsoft.com/powershell/module/failoverclusters/new-cluster?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-Cluster

## SYNOPSIS
Creates a new failover cluster.

## SYNTAX

```
New-Cluster [-Name] <String> [-IgnoreNetwork <StringCollection>] [-Node <StringCollection>] [-NoStorage]
 [-StaticAddress <StringCollection>]
```

## DESCRIPTION
The **New-Cluster** cmdlet creates a new failover cluster.
Before creating a cluster, the hardware (servers, networks, and storage) must be connected, and the validation tests must be run.

Use Test-Cluster to run the validation tests.
The tests will confirm that the hardware and settings are compatible with failover clustering.
There are multiple types of tests, including Inventory, System Configuration, Network, Storage, and other types of tests.

## EXAMPLES

### Example 1
```powershell
PS C:\> New-Cluster -Name cluster1 -Node node1,node2,node3,node4
```
```output
Name 
---- 
cluster1
```

This example creates a four-node cluster named cluster1, using default settings for IP addressing.

### Example 2
```powershell
PS C:\> New-Cluster -Name cluster1 -Node node1,node2 -NoStorage
```
```output
Name 
---- 
cluster1
```

This example creates a two-node cluster named cluster1.
The cluster will not have any clustered storage, or disk resources.
Storage can be added using the **Get-ClusterAvailableDisk** cmdlet with the **Add-ClusterDisk** cmdlet.

### Example 3
```powershell
PS C:\> New-Cluster -Name cluster1 -Node node1,node2,node3,node4 -StaticAddress 2.0.0.123
```
```output
Name 
---- 
cluster1
```

This example creates a four-node cluster named cluster1 that uses the static IP address 2.0.0.123.

### Example 4
```powershell
PS C:\> New-Cluster -Name cluster1 -Node node1,node2,node3,node4 -StaticAddress 2.0.0.123,3.0.0.123
```
```output
Name 
---- 
cluster1
```

This example creates a four-node cluster named cluster1 that uses the static IP addresses 2.0.0.123 and 3.0.0.123.

### Example 5
```powershell
PS C:\> New-Cluster -Name cluster1 -Node node1,node2,node3,node4 -IgnoreNetwork 2.0.0.0/8
```
```output
Name 
---- 
cluster1
```

This example creates a four-node cluster named cluster1.
The cluster uses default settings for IP addressing, and does not use the network 2.0.0.0/8.

### Example 6
```powershell
PS C:\> New-Cluster -Name cluster1 -Node node1,node2,node3,node4 -StaticAddress 2.0.0.123 -IgnoreNetwork 3.0.0.0/8
```
```output
Name 
---- 
cluster1
```

This example creates a four-node cluster named cluster1.
The cluster uses the static IP address 2.0.0.123, and does not use the network 3.0.0.0/8.

## PARAMETERS

### -IgnoreNetwork
Specifies one or more networks to ignore when running the cmdlet.
Networks with DHCP enabled are always included, but other networks need a static address to be specified using the **StaticAddress** parameter or should be explicitly ignored with this **IgnoreNetwork** parameter.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the cluster to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoStorage
Specifies that shared storage is ignored during the cluster creation.
The cluster created at the end of the operation will not have shared storage.
Shared storage can later be added by piping the **ClusterDiskInfo** object from the **Get-ClusterAvailableDisk** cmdlet into the **Add-ClusterDisk** cmdlet.

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

### -Node
Specifies a comma-separated list of cluster node names, or server names, on which to create the cluster.
If this parameter is not specified, then a one node cluster is created on the local physical computer.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StaticAddress
Specifies one or more static addresses to use when running the cmdlet.
Networks with DHCP enabled are always included, but other networks need a static address to be specified using the **StaticAddress** parameter or should be explicitly ignored with this **IgnoreNetwork** parameter.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## NOTES

- This cmdlet cannot be run remotely without Credential Security Service Provider (CredSSP) authentication on the server computer.
## RELATED LINKS

[Add-ClusterNode](./Add-ClusterNode.md)

[Get-Cluster](./Get-Cluster.md)

[Remove-Cluster](./Remove-Cluster.md)

[Start-Cluster](./Start-Cluster.md)

[Stop-Cluster](./Stop-Cluster.md)

[Test-Cluster](./Test-Cluster.md)

