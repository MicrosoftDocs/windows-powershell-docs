---
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/remove-hpcnode?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-HpcNode
---

# Remove-HpcNode

## SYNOPSIS
Removes the entry for one or more nodes from the HPC cluster management database.

## SYNTAX

### Name (Default)
```
Remove-HpcNode [-Comment <String>] [-Name] <String[]>
 [-Scheduler <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Node
```
Remove-HpcNode [-Comment <String>] -Node <HpcNode[]>
 [-Scheduler <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HpcNode** cmdlet removes the entry for one or more nodes from the HPC cluster management database.
This cmdlet does not delete Microsoft® HPC Pack on the nodes.
To delete a node completely, you must uninstall HPC Pack as well.
You can use HPC Cluster Manager to add nodes that you deleted back to the cluster.
HPC Cluster Manager is able to rediscover these deleted nodes.

## EXAMPLES

### Example 1: Remove a node
```
PS C:\>Remove-HpcNode -Name "Node11"
```

This command removes the node named Node11.

### Example 2: Removes nodes by name
```
PS C:\>Get-HpcNode -Name "hpcr1*" | Remove-HpcNode
```

This command gets **HpcNode** objects for all of the nodes with names that start with hpcr1, and removes those nodes.

## PARAMETERS

### -Comment
Specifies a comment for the node removal.

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

### -Name
Specifies an array of names for the nodes that you want to remove.
You cannot specify both the *Name* and the *Node* parameters.

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
Specifies an array of **HpcNode** objects for the nodes that you want to remove.
Use the Get-HpcNode cmdlet to get **HpcNode** objects for nodes.

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

## OUTPUTS

### None

## NOTES
* The built-in ConfirmImpact setting for this cmdlet is Medium. If this ConfirmImpact setting is equal to or higher than the value of the $ConfirmPreference variable for your environment, the cmdlet prompts for confirmation unless you specify `-Confirm:$False`. If this ConfirmImpact setting is lower than the value of the $ConfirmPreference variable for your environment, the cmdlet does not prompt for confirmation unless you specify `-Confirm` or `-Confirm:$True`.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcNode](./Get-HpcNode.md)

[Restart-HpcNode](./Restart-HpcNode.md)

[Set-HpcNode](./Set-HpcNode.md)

[Shutdown-HpcNode](./Shutdown-HpcNode.md)

[Start-HpcNode](./Start-HpcNode.md)
