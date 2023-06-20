---
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/restart-hpcnode?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-HpcNode
---

# Restart-HpcNode

## SYNOPSIS
Restarts a node that is already turned on.

## SYNTAX

### Name (Default)
```
Restart-HpcNode [-Comment <String>] [-Name] <String[]> [-Scheduler <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Node
```
Restart-HpcNode [-Comment <String>] -Node <HpcNode[]> [-Scheduler <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Restart-HpcNode** cmdlet restarts one or more nodes that are already turned on.
By default, this cmdlet sends a shutdown command to the operating system, but computer vendors can change the configuration to add commands based on Intelligent Platform Management Interface (IPMI).

## EXAMPLES

### Example 1: Restart a node by name
```
PS C:\>Restart-HpcNode -Name "hpc01cn01" -Comment "Restarting for maintenance."
```

This command restarts a node named hpc01cn01 and adds a comment for restarting.

### Example 2: Get nodes by template and restart them
```
PS C:\>Get-HpcNode -TemplateName "ApplicationA" | Restart-HpcNode
```

This command gets **HpcNode** objects for all of the nodes associated with the node template named applicationA, and restarts those nodes.
When you use certain templates for provisioning, you may need to restart the nodes.

## PARAMETERS

### -Comment
Specifies a comment for restarting the node.
This comment is recorded in the event log.

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
Specifies an array of the names of the nodes that you want to restart.
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
Specifies the **HpcNode** objects for the nodes that you want to restart.
Use the Get-HpcNode cmdlet to get the **HpcNode** object for a node.
You cannot specify both the Node and Name parameters.

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
* The built-in ConfirmImpact setting for this cmdlet is High. If this ConfirmImpact setting is equal to or higher than the value of the $ConfirmPreference variable for your environment, the cmdlet prompts for confirmation unless you specify `-Confirm:$False`. If this ConfirmImpact setting is lower than the value of the $ConfirmPreference variable for your environment, the cmdlet does not prompt for confirmation unless you specify `-Confirm` or `-Confirm:$True`.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcNode](./Get-HpcNode.md)

[Remove-HpcNode](./Remove-HpcNode.md)

[Set-HpcNode](./Set-HpcNode.md)

[Shutdown-HpcNode](./Shutdown-HpcNode.md)

[Start-HpcNode](./Start-HpcNode.md)
