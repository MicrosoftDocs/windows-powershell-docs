---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
Module Name: MSMQ
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/msmq/get-msmqqueuemanageracl?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-MsmqQueueManagerACL
---

# Get-MsmqQueueManagerACL

## SYNOPSIS
Gets access control lists for the local queue manager.

## SYNTAX

```
Get-MsmqQueueManagerACL [<CommonParameters>]
```

## DESCRIPTION
The **Get-MsmqQueueManagerACL** cmdlet gets an array of **MsmqQueueManagerAcl** objects for the local queue manager.

## EXAMPLES

### Example 1: Get message queue manager ACLs for the local queue manager
```
PS C:\> Get-MsmqQueueManagerACL
```

This command gets the message queue manager ACLs for the local queue manager.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Set-MsmqQueueManagerACL](./Set-MsmqQueueManagerACL.md)

