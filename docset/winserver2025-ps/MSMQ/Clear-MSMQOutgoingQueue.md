---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
Module Name: MSMQ
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/msmq/clear-msmqoutgoingqueue?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-MSMQOutgoingQueue
---

# Clear-MsmqOutgoingQueue

## SYNOPSIS
Clears outgoing queues.

## SYNTAX

```
Clear-MsmqOutgoingQueue -InputObject <OutgoingQueue[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Clear-MsmqOutgoingQueue** cmdlet clears outgoing queues.
Specify queues to clear by using **MsmqOutgoingQueue** objects.
This cmdlet returns an **MsmqOutgoingQueue** object that represents the cleared outgoing queue.

## EXAMPLES

### Example 1: Clear outgoing message queues based on name
```
PS C:\> Get-MsmqOutgoingQueue -Name "Order*" | Clear-MsmqOutgoingQueue
```

This command gets all the outgoing message queues that have names that start with the string Order by using the **Get-MsmqOutgoingQueue** cmdlet.
The command passes the results to the current cmdlet by using the pipeline operator.
The current cmdlet clears each queue.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies an array of **MsmqOutgoingQueue** objects.
This cmdlet clears outgoing queues that this parameter specifies.
This parameter accepts pipeline input.

```yaml
Type: OutgoingQueue[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Msmq.PowerShell.Commands.OutgoingQueue[]

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-MsmqOutgoingQueue](./Get-MSMQOutgoingQueue.md)

[Resume-MsmqOutgoingQueue](./Resume-MsmqOutgoingQueue.md)

[Suspend-MsmqOutgoingQueue](./Suspend-MsmqOutgoingQueue.md)

