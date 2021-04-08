---
author: Kateyanne
external help file: MSMQ_Cmdlets.xml
manager: dansimp
Module Name: MSMQ
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/msmq/remove-msmqqueue?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
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
PS C:\>Get-MsmqQueue -Name "Order*" -QueueType Public | Remove-MsmqQueue
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

