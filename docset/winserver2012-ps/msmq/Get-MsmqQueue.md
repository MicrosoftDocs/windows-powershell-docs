---
author: Kateyanne
external help file: MSMQ_Cmdlets.xml
manager: dansimp
Module Name: MSMQ
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/msmq/get-msmqqueue?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-MsmqQueue

## SYNOPSIS
Gets an array of MsmqQueue objects.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-MsmqQueue [[-Name] <String[]>] [-Journal] [-QueueType]
```

### UNNAMED_PARAMETER_SET_2
```
Get-MsmqQueue [[-Name] <String[]>] [-QueueType]
```

### UNNAMED_PARAMETER_SET_3
```
Get-MsmqQueue [[-Name] <String[]>] [-QueueType] [-SubQueue <String>]
```

## DESCRIPTION
The **Get-MsmqQueue** cmdlet gets an array of **MsmqQueue** objects, each of them representing an existing private, public or system queue.
The queue must be local to the machine on which this cmdlet runs.
If you do not specify any parameters this cmdlet will return all Public, Private and System Queues of the host machine.

## EXAMPLES

### Example 1: Get an array of MsmqQueue objects
```
PS C:\>Get-MsmqQueue -Name "Order*" -QueueType Private
```

This command gets an array of private MsmqQueue objects that are have the name Order.

## PARAMETERS

### -Journal
Indicates that this cmdlet gets the Journal queues that match the **Name** parameter.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a queue.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True(ByValue)
Accept wildcard characters: False
```

### -QueueType
Specifies the queue type.
If you specify this parameter as PrivateAndPublic, this cmdlet returns all public and private queues that match the **Name** parameter.
If you specify this parameter as Private, this cmdlet returns all private queues that match the **Name** parameter.
If you specify this parameter as Public, this cmdlet returns all public queues that match the **Name** parameter.
If you specify this parameter as SystemDeadLetter, this cmdlet returns all non-transactional dead letter queues that match the **Name** parameter.
If you specify this parameter as SystemJournal, this cmdlet returns all system journal queues that match the **Name** parameter. 

The acceptable values for this parameter are:
- PrivateAndPublic
- Private
- Public
- SystemJournal
- SystemDeadLetter
- SystemTransactionalDeadLetter

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: PrivateAndPublic, Private, Public, SystemJournal, SystemDeadLetter, SystemTransactionalDeadLetter

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubQueue
Specifies the **subqueue** object for the main queue.
If the subqueue doesn't exist, then this cmdlet will create one implicitly.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Clear-MsmqQueue](./Clear-MsmqQueue.md)

[New-MsmqQueue](./New-MsmqQueue.md)

[Receive-MsmqQueue](./Receive-MsmqQueue.md)

[Remove-MsmqQueue](./Remove-MsmqQueue.md)

[Send-MsmqQueue](./Send-MsmqQueue.md)

[Set-MsmqQueue](./Set-MsmqQueue.md)

