---
external help file: MSMQ_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 4450171C-8FBA-4A3F-B118-31FBDC9D2DCA
manager: dansimp
---

# Get-MsmqQueueACL

## SYNOPSIS
Gets an array of MsmqQueueAcl objects for the specified queues.

## SYNTAX

```
Get-MsmqQueueACL [-InputObject] <MessageQueue[]>
```

## DESCRIPTION
The **Get-MsmqQueueACL** cmdlet returns an array of **MsmqQueueAcl** objects for the specified queues.
This cmdlet can be applied to private, public, system journal, system dead-letter, and system transactional dead-letter queues.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -InputObject
Specifies an array of **MsmqQueue** objects that represent queues for which ACL information is returned.

```yaml
Type: MessageQueue[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-MsmqQueueACL](./Set-MsmqQueueACL.md)

