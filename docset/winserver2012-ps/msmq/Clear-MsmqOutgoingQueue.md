---
external help file: MSMQ_Cmdlets.xml
Module Name: MSMQ
online version: https://docs.microsoft.com/powershell/module/msmq/clear-msmqoutgoingqueue?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Clear-MsmqOutgoingQueue

## SYNOPSIS
Purges all outgoing queues that are represented by the supplied MsmqOutgoingQueue objects.

## SYNTAX

```
Clear-MsmqOutgoingQueue -InputObject <OutgoingQueue[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Clear-MsmqOutgoingQueue** cmdlet purges all outgoing queues that are represented by the supplied **MsmqOutgoingQueue** objects.
It returns an **MsmqOutgoingQueue** object that represents the cleared outgoing queue.

## EXAMPLES

### Example 1: Purge all outgoing queues
```
PS C:\>Get-MsmqOutgoingQueue -Name "Order*" | Clear-MsmqOutgoingQueue
```

This command gets all outgoing queue with a wildcard named Order and purges them.

## PARAMETERS

### -InputObject
Specifies an array of **MsmqOutgoingQueue** objects that represents an outgoing queue that is purged.

```yaml
Type: OutgoingQueue[]
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

[Get-MsmqOutgoingQueue](./Get-MsmqOutgoingQueue.md)

[Resume-MsmqOutgoingQueue](./Resume-MsmqOutgoingQueue.md)

[Suspend-MsmqOutgoingQueue](./Suspend-MsmqOutgoingQueue.md)

