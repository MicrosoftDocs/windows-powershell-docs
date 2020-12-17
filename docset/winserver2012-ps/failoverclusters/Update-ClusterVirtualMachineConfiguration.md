---
external help file: Failoverv2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: CC4C1119-2255-4E52-85B0-DDF5270C2180
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Update-ClusterVirtualMachineConfiguration

## SYNOPSIS
Refreshes the configuration of a clustered virtual machine within a failover cluster.

## SYNTAX

```
Update-ClusterVirtualMachineConfiguration [[-Name] <String>] [-Cluster <String>] [-InputObject <PSObject>]
 [-VMId <Guid>]
```

## DESCRIPTION
The **Update-ClusterVirtualMachineConfiguration** cmdlet refreshes the configuration of a clustered virtual machine within a failover cluster.
Use this cmdlet if a hardware device, such as a network adapter, is to be added or removed or the hardware configuration settings, such as the setting for virtual memory, are being changed for a clustered virtual machine.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Update-ClusterVirtualMachineConfiguration -Name "Virtual Machine Configuration VM1"
Name                State               Group               ResourceType 
----                -----               -----               ------------ 
Virtual Machine ... Online              Virtual Machine     Virtual Machine ...
```

This example refreshes the clustered virtual machine named Virtual Machine Configuration VM1 on the local cluster.

### EXAMPLE 2
```
PS C:\>Update-ClusterVirtualMachineConfiguration -Name "Virtual Machine Configuration VM2" -Cluster cluster1
Name                State               Group               ResourceType 
----                -----               -----               ------------ 
Virtual Machine ... Online              Virtual Machine     Virtual Machine
```

This example refreshes the clustered virtual machine named Virtual Machine Configuration VM2 on the cluster named cluster1.

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
Position: 1
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

## INPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## NOTES

## RELATED LINKS

[Add-ClusterVirtualMachineRole](./Add-ClusterVirtualMachineRole.md)

[Move-ClusterVirtualMachineRole](./Move-ClusterVirtualMachineRole.md)

