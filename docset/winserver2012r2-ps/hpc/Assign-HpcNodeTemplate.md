---
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/assign-hpcnodetemplate?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Assign-HpcNodeTemplate
---

# Assign-HpcNodeTemplate

## SYNOPSIS
Assigns or reapplies a node template to a node.

## SYNTAX

### NodeName-Template (Default)
```
Assign-HpcNodeTemplate [-Async] [-Rebuild] [[-Name] <String>] [-Template <HpcNodeTemplate>]
 -NodeName <String[]> [-Comment <String>] [-PassThru] [-Scheduler <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Node-Maintain
```
Assign-HpcNodeTemplate [-Async] [-Maintain] -Node <HpcNode[]> [-Comment <String>] [-PassThru]
[-Scheduler <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NodeName-Maintain
```
Assign-HpcNodeTemplate [-Async] [-Maintain] -NodeName <String[]> [-Comment <String>] [-PassThru][-Scheduler <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Node-Template
```
Assign-HpcNodeTemplate [-Async] [-Rebuild] [[-Name] <String>] [-Template <HpcNodeTemplate>] -Node <HpcNode[]>
 [-Comment <String>] [-PassThru] [-Scheduler <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HpcNodeTemplate** cmdlet assigns or reapplies a node template to one or more specified nodes.
As a result, the cmdlet rebuilds the nodes with the information from the node template.
This cmdlet is equivalent to clicking a node and then clicking Assign Node Template in HPC Cluster Manager.

## EXAMPLES

### Example 1: Apply a template to nodes in an unknown state
```
PS C:\>Get-HpcNode -State Unknown | Assign-HpcNodeTemplate -Name "DefaultNodeTemplate"
```

This command applies a node template named DefaultNodeTemplate to all of the nodes in the unknown state.

### Example 2: Asynchronously apply a node template to nodes in an unknown state
```
PS C:\>$WI = Get-HpcNode -State Unknown | Assign-HpcNodeTemplate -Name "DefaultNodeTemplate" -Async
PS C:\> Get-HpcOperation -WorkItem $WI
```

This command applies a node template named DefaultNodeTemplate asynchronously to all of the nodes in the unknown state.
Because the *Async* parameter is specified, this command returns an operation work item and stores that work item in the $W variable.
You can subsequently use $W to track the status of the operation.

The second command gets the operation for the work item in $WI.

## PARAMETERS

### -Async
Applies or reapplies the node template asynchronously.
The cmdlet exits without waiting for the nodes to finish provisioning.

If you specify the *Async* parameter, the *PassThru* parameter has no effect.
Also, the return type is an **HpcWorkItem** object when you specify *Async*.
You can use this **HpcWorkItem** object to track the status of the updates to the nodes.

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

### -Comment
Specifies a comment to use when the cmdlet reimages the node.
The comment appears in the Comments column of the operations lists that are available in HPC cluster manager.

The comment is not used if the other parameters for the cmdlet indicate that the cmdlet should not reimage the node.
For example, the comment is not used if you specify the *Maintain* parameter.

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

### -Maintain
Updates the specified nodes by incrementally reapplying the Maintain section of the node templates that are already associated with the nodes.
Specifying this parameter is equivalent to clicking the node and clicking Maintain in HPC Cluster Manager.
You cannot specify the *Maintain* parameter if you also specify the *Name*, *Template*, or *Rebuild* parameter.

```yaml
Type: SwitchParameter
Parameter Sets: Node-Maintain, NodeName-Maintain
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the node template to apply to the specified nodes.
You cannot specify the *Name* parameter if you also specify either the *Template* or the *Maintain* parameter.

```yaml
Type: String
Parameter Sets: NodeName-Template, Node-Template
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Node
Specifies an array of **HpcNode** objects for the nodes to which you want to assign or reapply the node templates.
Use the Get-HpcNode cmdlet to get the **HpcNode** objects for the nodes.
You cannot specify both the *Node* and *NodeName* parameters.

```yaml
Type: HpcNode[]
Parameter Sets: Node-Maintain, Node-Template
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NodeName
Specifies an array of the names of nodes to which you want to assign or reapply the node templates.
You cannot specify both the *NodeName* and *Node* parameters.
This parameter is a filter parameter, so you do not receive an error for specifying a node the does not exist in the HPC cluster as long as you specify at least one node that does exist.

```yaml
Type: String[]
Parameter Sets: NodeName-Template, NodeName-Maintain
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Causes the cmdlet to return the **HpcNode** objects for the specified nodes after the cmdlet applies the node templates to the nodes, and displays information about those nodes if you do not redirect the output of the cmdlet to another cmdlet or save the output in a variable.

The *PassThru* parameter has no effect if you also specify the *Async* parameter.
In that case, the cmdlet behaves as though you only specified the *Async* parameter.
If you specify the *PassThru* parameter and do not specify the *Async* parameter, the return type for the cmdlet consists of one or more **HpcNode** objects.

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

### -Rebuild
Rebuilds the operating system of the specified nodes by using the operating system image specified in the operating system reinstallation steps in the node template.
When you specify the *Rebuild* parameter, the **Assign-HpcNodeTemplate** cmdlet applies all of the steps in the node template, and not just the steps in the Maintain section of the node template.
When you specify the *Rebuild* parameter, the node template must contain the steps to reinstall an operating system image.

You cannot specify both the *Rebuild* and the *Maintain* parameters.

```yaml
Type: SwitchParameter
Parameter Sets: NodeName-Template, Node-Template
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that includes the nodes and node templates.
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

### -Template
Specifies an **HpcNodeTemplate** object for the node template that you want to apply to the specified nodes.
Use the Get-HpcNodeTemplate cmdlet to get the **HpcNodeTemplate** object for a node template.
You cannot specify the *Template* parameter if you also specify either the *Name* or the *Maintain* parameter.

```yaml
Type: HpcNodeTemplate
Parameter Sets: NodeName-Template, Node-Template
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

## OUTPUTS

### None, except as described for the Async and PassThru parameters.

## NOTES
* The specified nodes must be in the offline state before you can assign or reapply node templates to the nodes.
* If you reassign the node template that is already associated with the node to the node by explicitly specifying the node template with the *Name* or *Template* parameter, the **Assign-HpcNodeTemplate** behaves the same as if you specified the *Rebuild* parameter without specifying a node template.
* The built-in ConfirmImpact setting for this cmdlet is High. If this ConfirmImpact setting is equal to or higher than the value of the $ConfirmPreference variable for your environment, the cmdlet prompts for confirmation unless you specify `-Confirm:$False`. If this ConfirmImpact setting is lower than the value of the $ConfirmPreference variable for your environment, the cmdlet does not prompt for confirmation unless you specify `-Confirm` or `-Confirm:$True`.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Copy-HpcNodeTemplate](./Copy-HpcNodeTemplate.md)

[Export-HpcNodeTemplate](./Export-HpcNodeTemplate.md)

[Get-HpcNode](./Get-HpcNode.md)

[Get-HpcNodeTemplate](./Get-HpcNodeTemplate.md)

[Get-HpcOperation](./Get-HpcOperation.md)

[Import-HpcNodeTemplate](./Import-HpcNodeTemplate.md)

[New-HpcNodeTemplate](./New-HpcNodeTemplate.md)

[Remove-HpcNodeTemplate](./Remove-HpcNodeTemplate.md)
