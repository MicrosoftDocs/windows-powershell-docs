---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
Module Name: MSMQ
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/msmq/set-msmqqueuemanager?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-MsmqQueueManager
---

# Set-MsmqQueueManager

## SYNOPSIS
Configures the queue manager.

## SYNTAX

### All (Default)
```
Set-MsmqQueueManager [-RenewEncryptionKey] [-MsgStore <String>] [-MsgLogStore <String>]
 [-TransactionLogStore <String>] [-MessageQuota <Int64>] [-JournalQuota <Int64>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Connect
```
Set-MsmqQueueManager [-Connect] [-RenewEncryptionKey] [-MsgStore <String>] [-MsgLogStore <String>]
 [-TransactionLogStore <String>] [-MessageQuota <Int64>] [-JournalQuota <Int64>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Disconnect
```
Set-MsmqQueueManager [-Disconnect] [-RenewEncryptionKey] [-MsgStore <String>] [-MsgLogStore <String>]
 [-TransactionLogStore <String>] [-MessageQuota <Int64>] [-JournalQuota <Int64>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-MsmqQueueManager** cmdlet configures the properties of the Message Queuing (also known as MSMQ) queue manager.
This cmdlet returns a **QueueManager** object that represents the modified local queue manager.
If you specify the *RenewEncryptionKey* parameter to renew keys, you must restart the Message Queuing service for the new keys to become effective.

## EXAMPLES

### Example 1: Configure the queue manager
```
PS C:\> Set-MsmqQueueManager -MessageQuota 2048576 -MsgStore "C:\MSMQ\MessageFiles" -TransactionLogStore "C:\MSMQ\TransactionLogs"
```

This command configures properties of the Message Queuing queue manager.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Connect
Indicates that this cmdlet connects the computer to the network and to the directory service.
If you specify this parameter, you cannot specify the *Disconnect* parameter.

```yaml
Type: SwitchParameter
Parameter Sets: Connect
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Disconnect
Indicates that this cmdlet disconnects the computer from the network and from the directory service.
If you specify this parameter, you cannot specify the *Connect* parameter.

```yaml
Type: SwitchParameter
Parameter Sets: Disconnect
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JournalQuota
Specifies the total Journal Message Storage quota for Message Queuing.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MessageQuota
Specifies the total Message Storage quota for Message Queuing.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MsgLogStore
Indicates that this cmdlet changes the message logger storage location and moves over all the message logger files to the new location.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MsgStore
Specifies a new message storage location.
The cmdlet moves all the message files to the new location.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RenewEncryptionKey
Indicates that this cmdlet renews the public encryption key.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TransactionLogStore
Specifies a new transaction logger storage location.
This cmdlet moves all the transaction logger files to the new location.

```yaml
Type: String
Parameter Sets: (All)
Aliases: XactLogStore

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-MsmqQueueManager](./Get-MsmqQueueManager.md)

