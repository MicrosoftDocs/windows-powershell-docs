---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/23/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/start-clusterresource?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-ClusterResource
---

# Start-ClusterResource

## SYNOPSIS
Brings a resource online in a failover cluster.

## SYNTAX

```
Start-ClusterResource [[-Name] <String>] [-IgnoreLocked] [-ChooseBestNode] [-Wait <Int32>]
 [-InputObject <PSObject>] [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Start-ClusterResource` cmdlet brings a resource online in a failover cluster. Before the
resource is brought online, any resources that it depends are brought online.

## EXAMPLES

### Example 1

```powershell
Start-ClusterResource -Name "IP Address 172.24.11.0"
```

This example brings the resource called `IP Address 172.24.11.0` online on the local cluster. Before
bringing the resource online, this cmdlet brings online any resources on which the resource depends.

### Example 2

```powershell
Start-ClusterResource -Name "IP Address 172.24.11.0" -Wait 0
```

This example brings the resource called `IP Address 172.24.11.0` online on the local cluster. Before
bringing the resource online, this cmdlet brings online any resources on which the resource depends.
The Windows PowerShell prompt returns as soon as the action has been initiated.

## PARAMETERS

### -ChooseBestNode

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

### -IgnoreLocked

Specifies that locked groups are ignored when running the cmdlet.

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

Specifies the cluster resource to bring online.

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

Specifies the name of the cluster resource to bring online. This can also be the name of a Cluster
Shared Volume (CSV).

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

### -Wait

Specifies the time in seconds to wait for the cmdlet. If the **Wait** parameter isn't specified,
then the cmdlet waits for completion. If `-Wait 0` is specified, then the call is initiated and the
cmdlet returns without waiting.

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

### Microsoft.FailoverClusters.PowerShell.ClusterResource

### Microsoft.FailoverClusters.PowerShell.ClusterSharedVolume

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

### Microsoft.FailoverClusters.PowerShell.ClusterSharedVolume

## NOTES

## RELATED LINKS

[Add-ClusterResource](./Add-ClusterResource.md)

[Get-ClusterResource](./Get-ClusterResource.md)

[Move-ClusterResource](./Move-ClusterResource.md)

[Remove-ClusterResource](./Remove-ClusterResource.md)

[Resume-ClusterResource](./Resume-ClusterResource.md)

[Stop-ClusterResource](./Stop-ClusterResource.md)

[Suspend-ClusterResource](./Suspend-ClusterResource.md)
