---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.Adless.PowerShell.psm1-help.xml
Module Name: FailoverClusters
ms.date: 09/11/2024
online version: https://learn.microsoft.com/powershell/module/failoverclusters/add-workgroupclusternode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WorkgroupClusterNode
---

# Add-WorkgroupClusterNode

## SYNOPSIS
Adds a node to a workgroup cluster.

## SYNTAX

```
Add-WorkgroupClusterNode [-Node] <String[]> [-Credentials] <PSCredential[]> [-Name] <String>
 [-Credential] <PSCredential> [-NoStorage] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION

The `Add-WorkgroupClusterNode` cmdlet adds a node to a workgroup cluster.

## EXAMPLES

### EXAMPLE 1

```powershell
$params = @{
    Node = @("Node1", "Node2")
    Credentials = @($cred1, $cred2)
    Name = "Node3"
    Credential = $cred3
}
Add-WorkgroupClusterNode @params
```

This example adds `Node3` to the cluster whose membership is comprised of `Node1` and `Node2`.

## PARAMETERS

### -Node

An array of nodes to be added to the cluster.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credentials

An array of credentials for the nodes.

```yaml
Type: PSCredential[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

The name of the node to be added.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

The credential for the node to be added.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: True
Position: 4
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

[New-WorkgroupCluster](new-workgroupcluster.md)

[Remove-WorkgroupCluster](remove-workgroupcluster.md)

[Remove-WorkgroupClusterNode](remove-workgroupclusternode.md)

[Set-WorkgroupClusterRemotingConfiguration](set-workgroupclusterremotingconfiguration.md)

[Test-WorkgroupCluster](test-workgroupcluster.md)

[Test-WorkgroupClusterRemoting](test-workgroupclusterremoting.md)
