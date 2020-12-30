---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/27/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-MsmqQueueACL
ms.reviewer:
ms.assetid: 4450171C-8FBA-4A3F-B118-31FBDC9D2DCA
---

# Get-MsmqQueueACL

## SYNOPSIS
Gets queue access control lists.

## SYNTAX

```
Get-MsmqQueueACL [-InputObject] <MessageQueue[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-MsmqQueueACL** cmdlet gets **MsmqQueueAcl** objects.
The cmdlet applies to private, public, system journal, system dead-letter, and system transactional dead-letter queues.

## EXAMPLES

### Example 1: Get message queue ACLs
```
PS C:\> Get-MsmqQueue -Name "Order*" | Get-MsmqQueueACL
```

This command gets message queues that have names that start with Order by using the **Get-MsmqQueue** cmdlet.
The command passes the results to the current cmdlet by using the pipeline operator.
The current cmdlet gets ACLs for these queues.

## PARAMETERS

### -InputObject
Specifies an array of **MsmqQueue** objects.
The cmdlet gets access control list (ACL) information for queues that the **MsmqQueue** objects specify.
This parameter accepts pipeline input.

```yaml
Type: MessageQueue[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-MsmqQueue](./Get-MsmqQueue.md)

[Set-MsmqQueueACL](./Set-MsmqQueueACL.md)

