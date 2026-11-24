---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 03/13/2023
online version: https://learn.microsoft.com/powershell/module/failoverclusters/new-cluster?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-Cluster
---

# New-Cluster

## SYNOPSIS
Creates a new failover cluster.

## SYNTAX

```
New-Cluster [-Name] <String> [-Node <StringCollection>] [-StaticAddress <StringCollection>]
 [-IgnoreNetwork <StringCollection>] [-NoStorage] [-S2D]
 [-ManagementPointNetworkType <AdminAccessPointResType>]
 [-AdministrativeAccessPoint <AdminAccessPoint>] [-Force] [<CommonParameters>]
```

## DESCRIPTION

The `New-Cluster` cmdlet creates a new failover cluster. Before creating a cluster, the hardware
(servers, networks, and storage) must be connected, and the validation tests must be run.

Use Test-Cluster to run the validation tests. The tests will confirm that the hardware and settings
are compatible with failover clustering. There are multiple types of tests, including Inventory,
System Configuration, Network, Storage, and other types of tests.

> [!TIP]
> You should run the `New-Cluster` command from a cluster node or client that is the same version as
> the cluster nodes. Running `New-Cluster` from a lower-level (down-level) client computer may
> require `Update-ClusterFunctionalLevel` to be run after `New-Cluster` has been run.

## EXAMPLES

### Example 1

```powershell
New-Cluster -Name cluster1 -Node node1,node2,node3,node4
```

This example creates a four-node cluster named `cluster1`, using default settings for IP addressing.

### Example 2

```powershell
New-Cluster -Name cluster1 -Node node1,node2 -NoStorage
```

This example creates a two-node cluster named `cluster1`. The cluster will not have any clustered
storage, or disk resources. Storage can be added using the `Get-ClusterAvailableDisk` cmdlet with
the `Add-ClusterDisk` cmdlet.

### Example 3

```powershell
New-Cluster -Name cluster1 -Node node1,node2,node3,node4 -StaticAddress 2.0.0.123
```

This example creates a four-node cluster named `cluster1` that uses the static IP address
`2.0.0.123`.

### Example 4

```powershell
New-Cluster -Name cluster1 -Node node1,node2,node3,node4 -StaticAddress 2.0.0.123,3.0.0.123
```

This example creates a four-node cluster named `cluster1` that uses the static IP addresses
`2.0.0.123` and `3.0.0.123`.

### Example 5

```powershell
New-Cluster -Name cluster1 -Node node1,node2,node3,node4 -IgnoreNetwork 2.0.0.0/8
```

This example creates a four-node cluster named `cluster1`. The cluster uses default settings for IP
addressing, and doesn't use the network `2.0.0.0/8`.

### Example 6

```powershell
$parameters = @{
    Name = 'cluster1'
    Node = 'node1','node2','node3','node4'
    StaticAddress = '2.0.0.123'
    IgnoreNetwork = '3.0.0.0/8'
}
New-Cluster @parameters
```

This example creates a four-node cluster named cluster1. The cluster uses the static IP address
2.0.0.123, and doesn't use the network 3.0.0.0/8.

This example uses splatting to pass parameter values from the `$Parameters` variable to the command.
Learn more about [Splatting](/powershell/module/microsoft.powershell.core/about/about_splatting).

## PARAMETERS

### -AdministrativeAccessPoint

Specifies the type of administrative access point that the cmdlet creates for the cluster. The
acceptable values for this parameter are:

- **ActiveDirectoryAndDns**. The cmdlet creates an administrative access point for the cluster. The
  administrative access point is registered in DNS and enabled in Active Directory Domain Services.

- **Dns**. The cmdlet creates an administrative access point for the cluster. The administrative
  access point is registered in DNS but isn't enabled in Active Directory Domain Services.

- **None**.

The cmdlet doesn't create an administrative access point for the cluster. Some clustered roles and
functionality might not be available for a cluster that doesn't have an administrative access
point. Also, you cannot use Failover Cluster Manager to manage a cluster that doesn't have an
administrative access point.

```yaml
Type: AdminAccessPoint
Parameter Sets: (All)
Aliases: aap
Accepted values: None, ActiveDirectoryAndDns, Dns, ActiveDirectory

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

### -IgnoreNetwork

Specifies one or more networks to ignore when running the cmdlet. Networks with DHCP enabled are
always included, but other networks need a static address to be specified using the
**StaticAddress** parameter or should be explicitly ignored with this **IgnoreNetwork** parameter.

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

### -ManagementPointNetworkType
Specifies the network configuration used to determine IP address settings.

The acceptable values for this parameter are:

- Automatic: Automatically detects the appropriate setting. If SQL Server is running in Azure, uses `Distributed`. If SQL Server is running on-premises, uses `Singleton`. (Default setting)
- Singleton: The traditional method of DHCP or static IP address.
- Distributed: Uses a Distributed Network Name by using Node IP addresses.

```yaml
Type: AdminAccessPointResType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Automatic
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
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoStorage

Specifies that shared storage is ignored during the cluster creation. The cluster created at the end
of the operation will not have shared storage. Shared storage can later be added by piping the
**ClusterDiskInfo** object from the `Get-ClusterAvailableDisk` cmdlet into the `Add-ClusterDisk`
cmdlet.

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

Specifies a comma-separated list of cluster node names, or server names, on which to create the
cluster. If this parameter isn't specified, then a one node cluster is created on the local
physical computer.

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

### -S2D

Specifies whether to enable Storage Spaces Direct when creating the cluster.

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

### -StaticAddress

Specifies one or more static addresses to use when running the cmdlet. Networks with DHCP enabled
are always included, but other networks need a static address to be specified using the
**StaticAddress** parameter or should be explicitly ignored with this **IgnoreNetwork** parameter.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable,
-Verbose, -WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## NOTES

- This cmdlet cannot be run remotely without Credential Security Service Provider (CredSSP)
  authentication on the server computer.

## RELATED LINKS

[Add-ClusterNode](./Add-ClusterNode.md)

[Get-Cluster](./Get-Cluster.md)

[Remove-Cluster](./Remove-Cluster.md)

[Start-Cluster](./Start-Cluster.md)

[Stop-Cluster](./Stop-Cluster.md)

[Test-Cluster](./Test-Cluster.md)
