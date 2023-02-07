---
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/remove-hpcgroup?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-HpcGroup
---

# Remove-HpcGroup

## SYNOPSIS
Removes the association between one or more specified node groups and one or more specified nodes.

## SYNTAX

### Name (Default)
```
Remove-HpcGroup [-Name] <String[]> [-Node <HpcNode[]>] [-NodeName <String[]>]
[-Scheduler <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Id
```
Remove-HpcGroup [-Id] <Int32[]> [-Node <HpcNode[]>] [-NodeName <String[]>] [-Scheduler <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HpcGroup** cmdlet removes the association between one or more specified node groups and one or more specified nodes.

If you do not specify any nodes, **Remove-HpcGroup** removes the association between the specified node groups and all of the nodes that the node groups contain, then deletes the node groups.

If you specify all of the nodes in a specified node group, **Remove-HpcGroup** removes the association between the specified node group and all of the nodes, but does not delete the node group.

## EXAMPLES

### Example 1: Remove a node
```
PS C:\>Remove-HpcGroup -Name "MyNodeGroup" -NodeName "RetiringNode"
```

This command removes the node named RetiringNode from the node group named MyNodeGroup.

### Example 2: Remove the association between a node group and its nodes and remove the node group
```
PS C:\>Remove-HpcGroup -Name "MyRetiringNodeGroup"
```

This command removes the association between the node group named MyRetiringNodeGroup and all of the nodes that node group contains, and then deletes the node group.

### Example 3: Remove a node by its ID
```
PS C:\>Remove-HpcGroup -Id 26 -NodeName "RetiringNode2"
```

This command removes the node named RetiringNode2 from the node group with an identifier of 26.

### Example 4: Remove nodes from node groups
```
PS C:\>Get-HpcNode -Name "RetiringNode3,RetiringNode4" | Remove-HpcGroup -Name "NodeGroup1,NodeGroup2"
```

This command gets the **HpcNode** objects for the nodes named RetiringNode3 and RetiringNode4, then removes both of those nodes from the node groups named NodeGroup1 and NodeGroup2.

## PARAMETERS

### -Id
Specifies an array of node group IDs for node groups from which you want to remove the nodes.
Use the Get-HpcGroup cmdlet to view the node group IDs for node groups in the HPC cluster.
You cannot specify both the *Id* and *Name* parameters.

```yaml
Type: Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies an array of names for node groups from which you want to remove the nodes.
Use the Get-HpcGroup cmdlet to view the available node groups in the HPC cluster.
You cannot specify both the *Name* and *Id* parameters.

```yaml
Type: String[]
Parameter Sets: Name
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Node
Specifies an array of **HpcNode** objects for nodes that you want to remove from the node groups.
Use the Get-HpcNode cmdlet to get **HpcNode** objects for nodes.
You cannot specify both the *Node* and *NodeName* parameters.

```yaml
Type: HpcNode[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NodeName
Specifies an array of the names of nodes that you want to remove from the node groups.
You cannot specify both the *NodeName* and *Node* parameters.
This parameter is a filter parameter, so you do not receive an error for specifying a node the does not exist in the HPC cluster as long as you specify at least one node that does exist.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that includes the node groups.
The value must be a valid computer name or IP address.
If you do not specify the *Scheduler* parameter, this cmdlet uses the scheduler on the head node that the CCP_SCHEDULER environment variable specifies.
To set this environment variable, run the following cmdlet:

`Set-Content Env:CCP_SCHEDULER \<head_node_name\>`

```yaml
Type: String[]
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### HpcNode[]
This cmdlet accepts one or more **HpcNode** objects.

## OUTPUTS

### None

## NOTES
* The built-in ConfirmImpact setting for this cmdlet is High. If this ConfirmImpact setting is equal to or higher than the value of the $ConfirmPreference variable for your environment, the cmdlet prompts for confirmation unless you specify `-Confirm:$False`. If this ConfirmImpact setting is lower than the value of the $ConfirmPreference variable for your environment, the cmdlet does not prompt for confirmation unless you specify `-Confirm` or `-Confirm:$True`.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Add-HpcGroup](./Add-HpcGroup.md)

[Get-HpcGroup](./Get-HpcGroup.md)

[Get-HpcNode](./Get-HpcNode.md)

[New-HpcGroup](./New-HpcGroup.md)

[Set-HpcGroup](./Set-HpcGroup.md)
