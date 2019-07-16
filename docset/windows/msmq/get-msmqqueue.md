---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/27/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-MsmqQueue
ms.reviewer:
ms.assetid: 5735D84D-4C83-4350-A91B-5C0A0F009638
---

# Get-MsmqQueue

## SYNOPSIS
Gets message queues.

## SYNTAX

### All (Default)
```
Get-MsmqQueue [[-Name] <String[]>] [-QueueType <QueueType>] [<CommonParameters>]
```

### Journal
```
Get-MsmqQueue [[-Name] <String[]>] [-QueueType <QueueType>] [-Journal] [<CommonParameters>]
```

### SubQueue
```
Get-MsmqQueue [[-Name] <String[]>] [-QueueType <QueueType>] [-SubQueue <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-MsmqQueue** cmdlet gets an array of **MsmqQueue** objects.
Each **MsmqQueue** object represents an existing private, public, or system queue.
This cmdlet gets queues that are local to the computer where you run the cmdlet.
If you do not specify parameters, this cmdlet gets all public, private, and system queues of the host computer.

## EXAMPLES

### Example 1: Get public, private, and system queues
```
PS C:\> Get-MsmqQueue
```

This command gets public, private, and system queues for the host computer.

### Example 2: Get private queues
```
PS C:\> Get-MsmqQueue -Name "Order*" -QueueType Private
```

This command gets private queues that have names that start with the string Order for the host computer.

### Example 3: Get private Journal queues
```
PS C:\> Get-MsmqQueue -Name "Order*" -Journal -QueueType Private
```

This command gets private Journal queues that have names that start with the string Order for the host computer.

### Example 4: Get system Journal queues
```
PS C:\> Get-MsmqQueue -QueueType SystemJournal
```

This command gets system Journal queues for the host computer.

## PARAMETERS

### -Journal
Indicates that this cmdlet retrieves the Journal queue or queues that match the *Name* parameter.

```yaml
Type: SwitchParameter
Parameter Sets: Journal
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies an array of names of queues.
This parameter accepts wildcard characters.
The default value is *.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -QueueType
Specifies a queue type.
The acceptable values for this parameter are:

- PrivateAndPublic.
The cmdlet gets public and private queues that match the *Name* parameter. 
- Private.
The cmdlet gets private queues that match the *Name* parameter. 
- Public.
The cmdlet gets public queues that match the *Name* parameter. 
- SystemDeadLetter.
The cmdlet gets non-transactional dead-letter queues that match the *Name* parameter. 
- SystemJournal.
The cmdlet gets system journal queues that match the *Name* parameter. 
- SystemTransactionalDeadLetter.
The cmdlet gets transactional dead-letter queues that match the *Name* parameter. 

The default value is PrivateAndPublic.

```yaml
Type: QueueType
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
Specifies a subqueue object to get for the main queue.
If the subqueue does not exist, the cmdlet creates it implicitly.
The question mark (?) and asterisk (*) are not interpreted as wildcard characters, but as part of the subqueue name.

```yaml
Type: String
Parameter Sets: SubQueue
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Clear-MsmqQueue](./Clear-MSMQQueue.md)

[New-MsmqQueue](./New-MsmqQueue.md)

[Receive-MsmqQueue](./Receive-MsmqQueue.md)

[Remove-MsmqQueue](./Remove-MsmqQueue.md)

[Send-MsmqQueue](./Send-MsmqQueue.md)

[Set-MsmqQueue](./Set-MsmqQueue.md)

