---
external help file: CCPPSH.dll-Help.xml
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/set-hpcnodestate?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-HpcNodeState
---

# Set-HpcNodeState

## SYNOPSIS
Sets the state a node.

## SYNTAX

### Name (Default)
```
Set-HpcNodeState -State <String> [-Force] [-Async] [-Name] <String[]>
 [-Scheduler <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Node
```
Set-HpcNodeState -State <String> [-Force] [-Async] -Node <HpcNode[]>
 [-Scheduler <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-HpcNodeState** cmdlet sets the state of one or more nodes to online, offline, or rejected.

## EXAMPLES

### Example 1: Set the state of a node
```
PS C:\>Set-HpcNodeState -Name "MyNode" -State "Online"
```

This command sets the state of the node named MyNode to Online.

### Example 2: Force a node directly into Offline state
```
PS C:\>Set-HpcNodeState -Name "MyNode02" -State "Offline" -Force
```

This command forces the node named MyNode02 into the Offline state, without going into the draining state first.

### Example 3: Set the state for multiple nodes
```
PS C:\>Set-HpcNodeState -Name "MyNode03,MyNode04" -State "Offline" -Async
```

This command sets the state for the nodes named MyNode03 and MyNode04 to Offline, and returns without waiting for the state changes to take effect.

### Example 4: Get multiple nodes and set their state
```
PS C:\>Get-HpcNode -GroupName "MyTestNodes" | Set-HpcNodeState -State "Offline"
```

This command gets the **HpcNode** objects for the nodes in the node group named MyTestNodes, and sets the state for those nodes to Offline.

## PARAMETERS

### -Async
Specifies that the cmdlet should return immediately without waiting for the specified state to take effect.

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

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

### -Force
Forces the node to go offline without going into the draining state first.
You can only use this parameter when you specify Offline for the *State* parameter.

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

### -Name
Specifies an array of names of nodes for which you want to change the state.
You cannot specify both the *Name* and *Node* parameters.

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
Specifies an array of **HpcNode** objects for the nodes for which you want to change the state.
Use the Get-HpcNode cmdlet to get the **HpcNode** object for a node.
You cannot specify both the *Node* and *Name* parameters.

```yaml
Type: HpcNode[]
Parameter Sets: Node
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that includes the nodes.
The value must be a valid computer name or IP address.
If you do not specify the *Scheduler* parameter, this cmdlet uses the scheduler on the head node that the CCP_SCHEDULER environment variable specifies.

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

### -State
Specifies the new state that you want to assign to the nodes.
Valid value are:

- Online
- Offline
- Rejected

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
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

### One or more HpcNode objects if the Async parameter is not specified, or one or more HpcWorkItem objects if the Async parameter is specified.

## OUTPUTS

### HpcNode[]

## NOTES
If you set the state of a node to offline, the node can take a long time to go offline if jobs are running on the node. If any of the jobs have the Run until canceled property set, the operation to take the node offline does not return. Cancel such jobs before you set the state of the node to Offline.
The built-in ConfirmImpact setting for this cmdlet is Medium. If this ConfirmImpact setting is equal to or higher than the value of the $ConfirmPreference variable for your environment, the cmdlet prompts for confirmation unless you specify *Confirm:$False*. If this ConfirmImpact setting is lower than the value of the $ConfirmPreference variable for your environment, the cmdlet does not prompt for confirmation unless you specify *Confirm* or *Confirm:$True*.
You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcNode](/powershell/module/hpcpack2016/get-hpcnode?view=hpc16-ps)

[Set-HpcNode](./Set-HpcNode.md)
