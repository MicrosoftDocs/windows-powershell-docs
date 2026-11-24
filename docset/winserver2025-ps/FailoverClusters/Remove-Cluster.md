---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/remove-cluster?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Cluster
---

# Remove-Cluster

## SYNOPSIS
Destroys an existing failover cluster.

## SYNTAX

```
Remove-Cluster [[-Cluster] <String>] [-CleanupAD] [-Force] [-InputObject <PSObject>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Remove-Cluster` cmdlet destroys an existing failover cluster. The affected servers will no
longer function together as a cluster.

This cmdlet deletes all copies of the cluster configuration database on all cluster nodes.

Note: This cmdlet cannot be run remotely without Credential Security Service Provider (CredSSP)
authentication on the server computer.

## EXAMPLES

### Example 1

```powershell
Remove-Cluster
```

This example prompts the user for confirmation, then destroys the local failover cluster and removes
cluster configuration information from the cluster nodes.

### Example 2

```powershell
Remove-Cluster -Force
```

This example destroys the local failover cluster and removes cluster configuration information from
the cluster nodes. The cmdlet doesn't prompt for confirmation.

### Example 3

```powershell
Get-Cluster -Name Cluster1 | Remove-Cluster -Force -CleanupAD
```

This example destroys the cluster named `Cluster1`, removes cluster configuration information from
the cluster nodes, and deletes the cluster objects in Active Directory. The cmdlet doesn't prompt
for confirmation.

## PARAMETERS

### -CleanupAD

Specifies that when the cluster is destroyed, the objects in Active Directory that are associated
with the cluster are removed.

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

### -InputObject

Specifies the cluster to destroy.

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

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-Cluster](./Get-Cluster.md)

[New-Cluster](./New-Cluster.md)

[Start-Cluster](./Start-Cluster.md)

[Stop-Cluster](./Stop-Cluster.md)

[Test-Cluster](./Test-Cluster.md)
