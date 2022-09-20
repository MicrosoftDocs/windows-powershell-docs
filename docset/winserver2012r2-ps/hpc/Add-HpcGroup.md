---
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/add-hpcgroup?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-HpcGroup
---

# Add-HpcGroup

## SYNOPSIS
Adds nodes to node groups.

## SYNTAX

### Name-NodeName (Default)
```
Add-HpcGroup [-Name] <String[]> -NodeName <String[]>
 [-Scheduler <String[]>] [<CommonParameters>]
```

### Name-Node
```
Add-HpcGroup [-Name] <String[]> -Node <HpcNode[]> [-Scheduler <String[]>]
 [<CommonParameters>]
```

### Id-Node
```
Add-HpcGroup [-Id] <Int32[]> -Node <HpcNode[]> [-Scheduler <String[]>]
 [<CommonParameters>]
```

### Id-NodeName
```
Add-HpcGroup [-Id] <Int32[]> -NodeName <String[]> [-Scheduler <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-HpcGroup** cmdlet adds a specified list of one or more nodes to one or more specified node groups.
You can specify the node groups by name or by identifier.
You can specify the nodes either by name or by using **HpcNode** objects that you get with the Get-HpcNode cmdlet.

## EXAMPLES

### Example 1: Add a node to a node group
```
PS C:\>Add-HpcGroup -Name "MyNodeGroup" -NodeName "ComputeNode1"
```

This command adds the node named ComputeNode1 to the node group named MyNodeGroup.

### Example 2: Add a node by name and ID to a node group
```
PS C:\>Add-HpcGroup -Id 8 -NodeName "ComputeNode02"
```

This command adds the node named ComputeNode02 to the node group with a node group identifier of 8.

### Example 3: Get a node and add it to a group
```
PS C:\>Get-HpcNode -Name "ComputeNode03" | Add-HpcGroup -Name "MyNodeGroup"
```

This command gets an **HpcNode** object for the node named ComputeNode03, and then adds that node to the node group named MyNodeGroup.

### Example 4: Add multiple nodes to multiple groups
```
PS C:\>Add-HpcGroup -Name "NodeGroup01,NodeGroup02" -NodeName "ComputeNode04,ComputeNode05"
```

This command adds the nodes named ComputeNode04 and ComputeNode05 to the node groups named NodeGroup01 and NodeGroup02.

## PARAMETERS

### -Id
Specifies an array of node group identifiers for the node groups to which you want to add the nodes.
Use the Get-HpcGroup cmdlet to view a list of node groups for the cluster that includes their identifiers.
You cannot specify both the *Id* and *Name* parameters.

```yaml
Type: Int32[]
Parameter Sets: Id-Node, Id-NodeName
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies an array of names for the node groups to which you want to add the nodes.
Use the Get-HpcGroup cmdlet to view a list of node groups for the cluster that includes their names.
You cannot specify both the *Name* and *Id* parameters.
The maximum length for the name of a node group is 64 characters.

```yaml
Type: String[]
Parameter Sets: Name-NodeName, Name-Node
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Node
Specifies an array of **HpcNode** objects for the nodes that you want to add to the node groups.
Use the Get-HpcNode cmdlet to get **HpcNode** objects for the nodes.
You cannot specify both the *Node* and *NodeName* parameters.

```yaml
Type: HpcNode[]
Parameter Sets: Name-Node, Id-Node
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NodeName
Specifies an array of names for the nodes that you want to add to the node groups.
You cannot specify both the *NodeName* and *Node* parameters.
This parameter is a filter parameter, so you do not receive an error for specifying a node the does not exist in the HPC cluster as long as you specify at least one node that does exist.

```yaml
Type: String[]
Parameter Sets: Name-NodeName, Id-NodeName
Aliases:

Required: True
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### HpcNode[]

## OUTPUTS

### None

## NOTES
* Use this cmdlet to add nodes to a node group after you create the node group by using the New-HpcGroup cmdlet.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcGroup](./Get-HpcGroup.md)

[Get-HpcNode](./Get-HpcNode.md)

[New-HpcGroup](./New-HpcGroup.md)

[Remove-HpcGroup](./Remove-HpcGroup.md)

[Set-HpcGroup](./Set-HpcGroup.md)
