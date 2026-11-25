---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/add-clusterfileserverrole?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-ClusterFileServerRole
---

# Add-ClusterFileServerRole

## SYNOPSIS
Creates a clustered file server resource group.

## SYNTAX

```
Add-ClusterFileServerRole -Storage <StringCollection> [-StaticAddress <StringCollection>]
 [-IgnoreNetwork <StringCollection>] [[-Name] <String>] [-Wait <Int32>] [-InputObject <PSObject>]
 [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Add-ClusterFileServerRole` cmdlet creates a clustered file server resource group that
includes one or more disks, on which shared folders can be created for users.

When adding a clustered file server, specify a name for the file server, any IP address information
that isn't automatically supplied by your DHCP settings, and the storage volume or volumes that the
clustered file server should use.

> [!NOTE]
> This cmdlet cannot be run remotely without Credential Security Service Provider (CredSSP)
> authentication on the server computer.

## EXAMPLES

### Example 1: Create a clustered file server

```powershell
Add-ClusterFileServerRole -Storage "Cluster Disk 8"
```

This example creates a clustered file server using `Cluster Disk 8`, and assigns a default name.

### Example 2: Create and name a clustered file server

```powershell
Add-ClusterFileServerRole -Storage "Cluster Disk 6" -Name cluster1FS12
```

This example creates a clustered file server using `Cluster Disk 6`, and assigns the name
`cluster1FS12`.

### Example 3: Create a clustered file server with no waiting for resources

```powershell
Add-ClusterFileServerRole -Storage "Cluster Disk 8" -Wait 0
```

This example creates a clustered file server using `Cluster Disk 8`, and assigns a default name.
The cmdlet completes without waiting for all resources to come online.

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

### -InputObject

Specifies the cluster on which to create the highly available file server.

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

Specifies the name of the highly available file server to create.

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

### -Storage

Specifies the cluster disk resource to be added to the created highly available file server.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait

Specifies the time in seconds to wait for the cmdlet. If the **Wait** parameter isn't specified,
then the cmdlet waits for completion. If the value `0` is specified, then the call is initiated and
the cmdlet returns without waiting.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

## NOTES

## RELATED LINKS

[Add-ClusterScaleOutFileServerRole](./Add-ClusterScaleOutFileServerRole.md)

[Get-ClusterGroup](./Get-ClusterGroup.md)

[Move-ClusterGroup](./Move-ClusterGroup.md)

[Remove-ClusterGroup](./Remove-ClusterGroup.md)

[Start-ClusterGroup](./Start-ClusterGroup.md)

[Stop-ClusterGroup](./Stop-ClusterGroup.md)
