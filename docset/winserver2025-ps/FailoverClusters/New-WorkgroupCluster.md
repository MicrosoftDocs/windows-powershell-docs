---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.Adless.PowerShell.psm1-help.xml
Module Name: FailoverClusters
ms.date: 09/11/2024
online version: https://learn.microsoft.com/powershell/module/failoverclusters/new-workgroupcluster?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-WorkgroupCluster
---

# New-WorkgroupCluster

## SYNOPSIS
Creates a new workgroup cluster.

## SYNTAX

```
New-WorkgroupCluster [[-Node] <String[]>] [[-Credentials] <PSCredential[]>] [[-Name] <String>]
 [[-StaticAddress] <String[]>] [[-IgnoreNetwork] <String[]>]
 [[-ManagementPointNetworkType] <AdminAccessPointResType>]
 [[-AdministrativeAccessPoint] <AdminAccessPoint>] [-NoStorage] [-S2D] [-Force] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION

The `New-WorkgroupCluster` cmdlet creates a new workgroup cluster.

## EXAMPLES

### EXAMPLE 1

```powershell
New-WorkgroupCluster -Node "Node1", "Node2" -Credentials $cred1, $cred2 -Name "Cluster1"
```

This example creates a new workgroup cluster named `Cluster1` with `Node1` and `Node2` using
the credentials in `$cred1` and `$cred2`.

Note: Only None and DNS are supported for AdministrativeAccessPoint.

## PARAMETERS

### -Node

An array of nodes to be included in the cluster.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: @()
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credentials

An array of credentials for the nodes.

```yaml
Type: PSCredential[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

The name of the workgroup cluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StaticAddress

Specifies one or more static addresses to use when running the cmdlet. Networks with DHCP enabled
are always included, but other networks need a static address to be specified using the
**StaticAddress** parameter or should be explicitly ignored with this **IgnoreNetwork** parameter.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnoreNetwork

Specifies one or more networks to ignore when running the cmdlet. Networks with DHCP enabled are
always included, but other networks need a static address to be specified using the
**StaticAddress** parameter or should be explicitly ignored with this **IgnoreNetwork** parameter.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementPointNetworkType

Specifies the network configuration used to determine IP address settings. Acceptable values are:

- `Automatic`: Automatically detects the appropriate setting.
  - If SQL Server is running in Azure, it uses `Distributed`.
  - If SQL Server is running on-premises, it uses `Singleton`.
- `Singleton`: The traditional method of DHCP or static IP address.
- `Distributed`: Uses a Distributed Network Name by using Node IP addresses.

For on-prem SQL Server, if the value is set to `Automatic`, it defaults to `Singleton`.

```yaml
Type: AdminAccessPointResType
Parameter Sets: (All)
Aliases:
Accepted values: Automatic, Singleton, Distributed

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdministrativeAccessPoint

Specifies the type of administrative access point that the cmdlet creates for the cluster.
Acceptable values are:

- `DNS`: The cmdlet creates an administrative access point for the cluster. The administrative
  access point is registered in DNS but isn't enabled in Active Directory Domain Services.
- `None`

The cmdlet doesn't create an administrative access point for the cluster. Some clustered roles and
functionality might not be available for a cluster that doesn't have an administrative access
point. Also, you cannot use Failover Cluster Manager to manage a cluster that doesn't have an
administrative access point.

```yaml
Type: AdminAccessPoint
Parameter Sets: (All)
Aliases:
Accepted values: None, Dns

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoStorage

Specifies that shared storage is ignored for the workgroup cluster node.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -S2D

Specifies whether to enable Storage Spaces Direct when creating the workgroup cluster.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WorkgroupClusterNode](add-workgroupclusternode.md)

[Remove-WorkgroupCluster](remove-workgroupcluster.md)

[Remove-WorkgroupClusterNode](remove-workgroupclusternode.md)

[Set-WorkgroupClusterRemotingConfiguration](set-workgroupclusterremotingconfiguration.md)

[Test-WorkgroupCluster](test-workgroupcluster.md)

[Test-WorkgroupClusterRemoting](test-workgroupclusterremoting.md)
