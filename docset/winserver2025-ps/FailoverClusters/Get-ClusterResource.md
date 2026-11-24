---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/get-clusterresource?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ClusterResource
---

# Get-ClusterResource

## SYNOPSIS
Gets information about one or more resources in a failover cluster.

## SYNTAX

```
Get-ClusterResource [[-Name] <StringCollection>] [-VMId <Guid>] [-InputObject <PSObject>]
 [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Get-ClusterResource` cmdlet gets information about one or more resources in a failover
cluster.

To set a common property for a clustered resource, use this cmdlet to get the object for the
clustered resource, and then set the appropriate property on that object directly. To get and set
more specific information about a clustered resource, use this cmdlet with `Get-ClusterParameter`
and `Set-ClusterParameter`.

## EXAMPLES

### Example 1

```powershell
Get-ClusterResource
```

This example lists all cluster resources on the local cluster.

### Example 2

```powershell
Get-ClusterResource -Name "Cluster Disk 2" | Format-List -Property *
```

This example displays information about `Cluster Disk 2`, on the local cluster, in the form of a
list.

### Example 3

```powershell
Get-ClusterResource -Name "Cluster Disk 2" | Get-ClusterParameter
```

This example displays detailed parameters for `Cluster Disk 2` on the local cluster.

### Example 4

```powershell
Get-ClusterGroup -Name FileServer1 | Get-ClusterResource
```

This example lists cluster resources in cluster group named `FileServer1`, a clustered file server
on the local cluster.

### Example 5

```powershell
Get-ClusterResource -Name "Cluster Disk 2" | ForEach-Object -Process {
    $_.RestartDelay = 600
}
```

This example sets the common property `RestartDelay` for the `Cluster Disk 2` resource on the local
cluster to `600`.

### Example 6

```powershell
Get-ClusterResource -Name "cluster pool 1" | Format-List -Property OwnerNode
```

This example shows how to display the owner of a cluster pooled disk.

### Example 7

```powershell
Get-ClusterResource -Name *print-VM1 | Get-VM | Stop-VM -Verbose -Confirm:$false
```

This example enumerates the cluster resources for wildcard characters `*print-VM1` and stops the
corresponding virtual machines without user confirmation. Verbose mode is turned on for details of
the operation.

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

### -InputObject

Specifies the cluster node or cluster group on which to enumerate cluster resources.

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

### -Name

Specifies the name of the cluster resource to get.

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

### -VMId

Specifies the virtual machine identifier (ID).

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

### Microsoft.FailoverClusters.PowerShell.ClusterResource

### Microsoft.FailoverClusters.PowerShell.ClusterNode

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## NOTES

## RELATED LINKS

[ForEach-Object](https://go.microsoft.com/fwlink/?LinkID=113300)

[Format-List](https://go.microsoft.com/fwlink/?LinkID=113302)

[Add-ClusterResource](./Add-ClusterResource.md)

[Move-ClusterResource](./Move-ClusterResource.md)

[Remove-ClusterResource](./Remove-ClusterResource.md)

[Resume-ClusterResource](./Resume-ClusterResource.md)

[Start-ClusterResource](./Start-ClusterResource.md)

[Stop-ClusterResource](./Stop-ClusterResource.md)

[Suspend-ClusterResource](./Suspend-ClusterResource.md)
