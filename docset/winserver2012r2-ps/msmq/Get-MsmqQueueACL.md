---
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
Module Name: MSMQ
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/msmq/get-msmqqueueacl?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-MsmqQueueACL
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

### Example 1
```
PS C:\>Get-MsmqQueue -Name "Order*" | Get-MsmqQueueACL
```

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-MsmqQueueACL](./Set-MsmqQueueACL.md)

