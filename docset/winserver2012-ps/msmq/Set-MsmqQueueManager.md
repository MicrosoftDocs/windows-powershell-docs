---
external help file: MSMQ_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: A327DEB3-B1F6-43F4-93B8-A73B5A78DF13
manager: dansimp
---

# Set-MsmqQueueManager

## SYNOPSIS
Configures the properties of the specified queue manager.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-MsmqQueueManager [-Connect] [-JournalQuota <Int64>] [-MessageQuota <Int64>] [-MsgLogStore <String>]
 [-MsgStore <String>] [-RenewEncryptionKey] [-TransactionLogStore <String>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-MsmqQueueManager [-Disconnect] [-JournalQuota <Int64>] [-MessageQuota <Int64>] [-MsgLogStore <String>]
 [-MsgStore <String>] [-RenewEncryptionKey] [-TransactionLogStore <String>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Set-MsmqQueueManager [-JournalQuota <Int64>] [-MessageQuota <Int64>] [-MsgLogStore <String>]
 [-MsgStore <String>] [-RenewEncryptionKey] [-TransactionLogStore <String>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-MsmqQueueManager** cmdlet is used to configure the properties of the specified MSMQ queue manager.
After renewing the encryption keys through the parameter **RenewEncryptionKey**, the user must restart the MSMQ service for the new keys to become effective.
This cmdlet returns a **QueueManager** object that represents the modified local queue manager.

## EXAMPLES

### Example 1: Specify properties for the specified queue manager
```
PS C:\>Set-MsmqQueueManager -MessageQuota 2048576 -MsgStoreLocation "c:\MSMQ\MessageFiles" -TransactionLogStore "c:\MSMQ\XactLogs"
```

This command specifies the message quota, message store location, and transaction log store for the default queue.

## PARAMETERS

### -Connect
Indicates that this cmdlet connects the computer to the network and to the directory service.
This parameter cannot be specified if the **Disconnect** parameter is specified.

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

### -Disconnect
Indicates that this cmdlet disconnects the computer from the network and from the directory service.
This parameter cannot be specified if the **Connect** parameter is specified.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JournalQuota
Specifies the total Journal Message Storage quota for MSMQ.

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
Specifies the total Message Storage quota for MSMQ.

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
Specifies a new location for the message storage and moves over all the message files to the new location.

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
Specifies the transaction logger storage location and moves over all the transaction logger files to the new location.

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

[Get-MsmqQueueManager](./Get-MsmqQueueManager.md)

