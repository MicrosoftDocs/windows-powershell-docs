---
author: Kateyanne
external help file: MSMQ_Cmdlets.xml
manager: dansimp
Module Name: MSMQ
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/msmq/clear-msmqqueue?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Clear-MsmqQueue

## SYNOPSIS
Clears all queues that are represented by the supplied MessageQueue objects.

## SYNTAX

```
Clear-MsmqQueue -InputObject <MessageQueue[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Clear-MsmqQueue** cmdlet clears all queues that are represented by the supplied **MessageQueue** objects.
It returns a **MessageQueue** object that represents the cleared outgoing queue.

## EXAMPLES

### Example 1: Clear all queues under a specified wildcard
```
PS C:\>Get-MessageQueue -Name Order* | Clear-MessageQueue
```

This command gets all queue under the wildcard named Order, then clears them.

## PARAMETERS

### -InputObject
Specifies a **MessageQueue** object that represents a queue that will be purged.

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

[Get-MsmqQueue](./Get-MsmqQueue.md)

[New-MsmqQueue](./New-MsmqQueue.md)

[Receive-MsmqQueue](./Receive-MsmqQueue.md)

[Remove-MsmqQueue](./Remove-MsmqQueue.md)

[Send-MsmqQueue](./Send-MsmqQueue.md)

[Set-MsmqQueue](./Set-MsmqQueue.md)

