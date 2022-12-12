---
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
Module Name: MSMQ
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/msmq/suspend-msmqoutgoingqueue?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-MsmqOutgoingQueue
---

# Suspend-MsmqOutgoingQueue

## SYNOPSIS
Pauses outgoing queues.

## SYNTAX

```
Suspend-MsmqOutgoingQueue -InputObject <OutgoingQueue[]> [<CommonParameters>]
```

## DESCRIPTION
The **Suspend-MsmqOutgoingQueue** cmdlet pauses outgoing queues.
Specify queues to pause by using **MsmqOutgoingQueue** objects.
This cmdlet returns the suspended queue objects.

## EXAMPLES

### Example 1
```
PS C:\>Get-MsmqOutgoingQueue -Name "Order*" | Suspend-MsmqOutgoingQueue
```

## PARAMETERS

### -InputObject
Specifies an array of **MsmqOutgoingQueue** objects.
This cmdlet pauses outgoing queues that this parameter specifies.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Clear-MsmqOutgoingQueue](./Clear-MSMQOutgoingQueue.md)

[Get-MsmqOutgoingQueue](./Get-MSMQOutgoingQueue.md)

[Resume-MsmqOutgoingQueue](./Resume-MsmqOutgoingQueue.md)

