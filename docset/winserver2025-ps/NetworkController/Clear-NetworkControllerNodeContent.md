---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-Help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/clear-networkcontrollernodecontent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-NetworkControllerNodeContent
---

# Clear-NetworkControllerNodeContent

## SYNOPSIS
Clears Network Controller settings from a Network Controller node.

## SYNTAX

```
Clear-NetworkControllerNodeContent [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Clear-NetworkControllerNodeContent** cmdlet is used to clear Network Controller settings from a Network Controller node.

Consider a scenario where you want to remove a node from the cluster, and the node is not reachable over the network.
You can still remove the node using **Remove-NetworkControllerNode** command, but to remove local settings from the node, you must execute **Clear-NetworkControllerNodecontent** cmdlet locally on the removed node.

Additionally, the Network Controller configuration may fail before configuration is complete.
If the configuration is partially complete on one or more nodes, run this cmdlet locally on the nodes to remove the configuration.
In these cases, the Network Controller configuration error message will inform you to run this cmdlet on specific nodes.

Do not execute this cmdlet to remove a node from the cluster.
Use **Remove-NetworkControllerNode** for that purpose.

## EXAMPLES


## PARAMETERS

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
Forces the command to run without asking for user confirmation.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Remove-NetworkControllerNode](./Remove-NetworkControllerNode.md)

