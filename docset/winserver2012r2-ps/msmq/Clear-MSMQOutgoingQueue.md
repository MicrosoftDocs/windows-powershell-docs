---
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
Module Name: MSMQ
online version: 
schema: 2.0.0
title: Clear-MSMQOutgoingQueue
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 67BE94A0-781F-4AA1-8CAC-43E03BC71C4A
ms.author: kenwith
ms.reviewer: brianlic
---

# Clear-MsmqOutgoingQueue

## SYNOPSIS
Purges outgoing queues.

## SYNTAX

```
Clear-MsmqOutgoingQueue -InputObject <OutgoingQueue[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Clear-MsmqOutgoingQueue** cmdlet purges outgoing queues.
Specify queues to purge by using **MsmqOutgoingQueue** objects.
This cmdlet returns an **MsmqOutgoingQueue** object that represents the cleared outgoing queue.

## EXAMPLES

### Example 1
```
PS C:\>Get-MsmqOutgoingQueue -Name "Order*" | Clear-MsmqOutgoingQueue
```

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
This cmdlet purges outgoing queues that this parameter specifies.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-MsmqOutgoingQueue](./Get-MSMQOutgoingQueue.md)

[Resume-MsmqOutgoingQueue](./Resume-MsmqOutgoingQueue.md)

[Suspend-MsmqOutgoingQueue](./Suspend-MsmqOutgoingQueue.md)

