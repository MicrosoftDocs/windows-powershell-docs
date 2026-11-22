---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/23/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/stop-cluster?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Cluster
---

# Stop-Cluster

## SYNOPSIS
Stops the Cluster service on all nodes in a failover cluster, which will stop all services and
applications configured in the cluster.

## SYNTAX

### Cluster name (Default)

```
Stop-Cluster [[-Cluster] <String>] [-Force] [-Wait <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject

```
Stop-Cluster [-Force] [-Wait <Int32>] [-InputObject <PSObject>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The `Stop-Cluster` cmdlet stops the Cluster service on all nodes in a failover cluster, which will
stop all services and applications configured in the cluster. A node can only function as part of
the cluster when the Cluster service is running on that node.

## EXAMPLES

### Example 1: Stop Cluster service on all nodes of the local cluster

```powershell
Stop-Cluster
```

This example stops the Cluster service on all nodes in the local cluster, which will stop all
services and applications configured in the cluster.

### Example 2: Stop Cluster service on all nodes of a cluster

```powershell
Stop-Cluster -Name cluster1
```

This example stops the Cluster service on all nodes in the cluster named `cluster1`, which will stop
all services and applications configured in the cluster.

## PARAMETERS

### -Cluster

Specifies the name of the cluster on which to run this cmdlet. If the input for this parameter is
`.` or it is omitted, then the cmdlet runs on the local cluster.

```yaml
Type: String
Parameter Sets: Cluster name
Aliases: Name

Required: False
Position: 0
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
Default value: None
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

### -InputObject

Specifies the cluster to stop.

```yaml
Type: PSObject
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### None

## NOTES

## RELATED LINKS

[Get-Cluster](./Get-Cluster.md)

[New-Cluster](./New-Cluster.md)

[Remove-Cluster](./Remove-Cluster.md)

[Start-Cluster](./Start-Cluster.md)

[Test-Cluster](./Test-Cluster.md)
