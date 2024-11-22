---
external help file: CCPPSH.dll-Help.xml
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/shutdown-hpcnode?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Shutdown-HpcNode
---

# Shutdown-HpcNode

## SYNOPSIS
Turns off one or more nodes.

## SYNTAX

### Name (Default)
```
Shutdown-HpcNode [-Comment <String>] [-Name] <String[]>
 [-Scheduler <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Node
```
Shutdown-HpcNode [-Comment <String>] -Node <HpcNode[]>
 [-Scheduler <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Shutdown-HpcNode** cmdlet turns off one or more nodes.
If you do not have an Intelligent Platform Management Interface (IPMI) script that your computer vendor configured, you may not be able to start the node again remotely.
By default, this cmdlet sends a shutdown command to the operating system, but computer vendors can change the configuration to add IPMI-based commands.

## EXAMPLES

### Example 1: Shut down the nodes in a group
```
PS C:\>Get-HpcNode -GroupName "Old" | Shutdown-HpcNode
```

This command gets the **HpcNode** objects for all nodes in the node group named Old and shuts down those nodes.

### Example 2: Shut down a node by name
```
PS C:\>Shutdown-HpcNode -Name "MyComputeNode"
```

This command shuts down the node named MyComputeNode.

## PARAMETERS

### -Comment
Specifies a comment that provides a reason that you turned off the nodes.

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
Specifies an array of the names of the nodes that you want to turn off.
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
Specifies an array  of **HpcNode** objects that correspond to the nodes that you want to turn off.
Use the Get-HpcNode cmdlet to get an **HpcNode** object for a node.
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

### HpcNode[] objects

## OUTPUTS

### None

## NOTES
* The built-in ConfirmImpact setting for this cmdlet is High. If this ConfirmImpact setting is equal to or higher than the value of the $ConfirmPreference variable for your environment, the cmdlet prompts for confirmation unless you specify `-Confirm:$False`. If this ConfirmImpact setting is lower than the value of the $ConfirmPreference variable for your environment, the cmdlet does not prompt for confirmation unless you specify `-Confirm` or `-Confirm:$True`.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcNode](/powershell/module/hpcpack2016/get-hpcnode?view=hpc16-ps)

[Remove-HpcNode](/powershell/module/hpcpack2016/remove-hpcnode?view=hpc16-ps)

[Restart-HpcNode](/powershell/module/hpcpack2016/restart-hpcnode?view=hpc16-ps)

[Set-HpcNode](./Set-HpcNode.md)

[Start-HpcNode](./Start-HpcNode.md)
