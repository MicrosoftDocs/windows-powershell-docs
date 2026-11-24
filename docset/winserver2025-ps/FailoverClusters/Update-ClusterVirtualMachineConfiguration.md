---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/23/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/update-clustervirtualmachineconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-ClusterVirtualMachineConfiguration
---

# Update-ClusterVirtualMachineConfiguration

## SYNOPSIS
Refreshes the configuration of a clustered virtual machine within a failover cluster.

## SYNTAX

```
Update-ClusterVirtualMachineConfiguration [[-Name] <String>] [-VMId <Guid>]
 [-InputObject <PSObject>] [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Update-ClusterVirtualMachineConfiguration` cmdlet refreshes the configuration of a clustered
virtual machine within a failover cluster. Use this cmdlet if a hardware device, such as a network
adapter, is to be added or removed or the hardware configuration settings, such as the setting for
virtual memory, are being changed for a clustered virtual machine.

## EXAMPLES

### Example 1: Refresh a clustered virtual machine on the local cluster

```powershell
Update-ClusterVirtualMachineConfiguration -Name "Virtual Machine Configuration VM1"
```

This example refreshes the clustered virtual machine named `Virtual Machine Configuration VM1` on
the local cluster.

### Example 2: Refresh a clustered virtual machine on a cluster

```powershell
$parameters = @{
    Name = 'Virtual Machine Configuration VM2'
    Cluster = 'cluster1'
}
Update-ClusterVirtualMachineConfiguration @parameters
```

This example refreshes the clustered virtual machine named `Virtual Machine Configuration VM2` on
the cluster named `cluster1`. The example uses splatting to pass parameter values from
the `$Parameters` variable to the command. Learn more about
[Splatting](/powershell/module/microsoft.powershell.core/about/about_splatting).

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

Specifies the clustered virtual machine resource to update.

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

Specifies the name of the clustered virtual machine resource to update.

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

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## NOTES

## RELATED LINKS

[Add-ClusterVirtualMachineRole](./Add-ClusterVirtualMachineRole.md)

[Move-ClusterVirtualMachineRole](./Move-ClusterVirtualMachineRole.md)
