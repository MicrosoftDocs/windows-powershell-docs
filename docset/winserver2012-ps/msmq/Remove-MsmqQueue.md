---
external help file: MSMQ_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 65884D1F-717E-4B91-96D3-3BA21329D1DC
manager: dansimp
---

# Remove-MsmqQueue

## SYNOPSIS
Removes specified queues from the supplied MsmqQueue objects.

## SYNTAX

```
Remove-MsmqQueue -InputObject <MessageQueue[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-MsmqQueue** cmdlet removes queues that are represented by the supplied **MsmqQueue** objects.
The cmdlet has no return value.

## EXAMPLES

### Example 1: Remove a queue
```
PS C:\>Get-MsmqQueue â€"Name "Order*" â€"QueueType Public | Remove-MsmqQueue
```

This command removes all public queues that contain the wildcard name Order*.

## PARAMETERS

### -InputObject
Specifies an array of **MsmqQueue** objects that represent the queues that will be removed.
This parameter accepts pipelined input.

```yaml
Type: MessageQueue[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

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
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Clear-MsmqQueue](./Clear-MsmqQueue.md)

[Get-MsmqQueue](./Get-MsmqQueue.md)

[New-MsmqQueue](./New-MsmqQueue.md)

[Receive-MsmqQueue](./Receive-MsmqQueue.md)

[Send-MsmqQueue](./Send-MsmqQueue.md)

[Set-MsmqQueue](./Set-MsmqQueue.md)

