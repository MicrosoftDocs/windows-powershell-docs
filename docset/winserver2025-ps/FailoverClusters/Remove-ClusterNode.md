---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 10/21/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/remove-clusternode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ClusterNode
---

# Remove-ClusterNode

## SYNOPSIS
Removes a node from a failover cluster.

## SYNTAX

```
Remove-ClusterNode [[-Name] <StringCollection>] [-Force] [-Wait <Int32>]
 [-IgnoreStorageConnectivityLoss] [-CleanupDisks] [-InputObject <PSObject>] [-Cluster <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Remove-ClusterNode` cmdlet removes a node from a failover cluster. After the node is removed,
the node no longer functions as part of the cluster unless the node is added back to the cluster.
Removing a node is also called evicting a node from the cluster.

Note: This cmdlet cannot be run remotely without Credential Security Service Provider (CredSSP)
authentication on the server computer.

## EXAMPLES

### Example 1

```powershell
Remove-ClusterNode -Name node4
```

This example removes the node named `node4` from the local cluster.

### Example 2

```powershell
Remove-ClusterNode -Name node4 -Force
```

This example removes the node named `node4` from the local cluster without prompting for
confirmation.

## PARAMETERS

### -CleanupDisks

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

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Runs the cmdlet without prompting for confirmation. By default the cmdlet will ask for confirmation
from the user before proceeding.

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

### -IgnoreStorageConnectivityLoss

Indicates that this cmdlet doesn't check whether the cluster node contains non-shared storage, if
Storage Spaces Direct is enabled. If you don't specify this parameter, the cmdlet checks whether
this node has any Storage Spaces Direct storage. If this cmdlet finds Storage Spaces Direct storage,
it prompts you for confirmation before it removes the node.

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

Specifies the cluster node to remove.

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

Specifies the name of the cluster node to remove.

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

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

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
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterNode

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-ClusterNode](./Add-ClusterNode.md)

[Get-ClusterNode](./Get-ClusterNode.md)

[Resume-ClusterNode](./Resume-ClusterNode.md)

[Start-ClusterNode](./Start-ClusterNode.md)

[Stop-ClusterNode](./Stop-ClusterNode.md)

[Suspend-ClusterNode](./Suspend-ClusterNode.md)
