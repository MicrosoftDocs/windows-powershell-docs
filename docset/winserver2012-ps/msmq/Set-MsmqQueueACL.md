---
external help file: MSMQ_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 4DAF0FE1-6D1E-4F47-8441-78DEFDB24512
manager: dansimp
---

# Set-MsmqQueueACL

## SYNOPSIS
Sets the access rights of specified queues.

## SYNTAX

```
Set-MsmqQueueACL [-InputObject] <MessageQueue[]> [-Allow <MessageQueueAccessRights>]
 [-Deny <MessageQueueAccessRights>] [-Remove <MessageQueueAccessRights>] -UserName <String[]> [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Set-MsmqQueueACL** cmdlet sets the access rights of the specified queues.
This cmdlet returns the updated **MsmqQueueAcl** object.
This cmdlet can be applied to private, public, journal, system journal, system dead-letter, and system transactional dead-letter queues.

## EXAMPLES

### Example 1: Set the access rights for the specified queue
```
PS C:\>Get-MsmqQueue â€"Name "Order*" â€"QueueType Private | Set-MsmqQueueAcl â€"UserName "REDMOND\pattiful" â€"Allow Delete,Peek,Receive,Send â€"Deny TakeOwnership
```

This command sets Allow, Delete, Peek, Receive, and Send access rights for user pattiful on all queues that have the wildcard named Order*.

## PARAMETERS

### -Allow
Specifies the permissions that are granted to the supplied user account or group.

The acceptable values for this parameter are:

- Delete: Delete the specified queue. 
- FullControl: Full control of the specified queue. 
- GetPermissions: Get the permissions of the specified queue. 
- GetProperties: Get the properties of the specified queue. 
- JournalReceive: Receive a message from the specified queue's journal queue. 
- Peek: Peek a message from the specified queue. 
- Receive: Receive a message from the specified queue. 
- Send: Send a message to the specified queue. 
- SetPermissions: Set the permissions of the specified queue. 
- SetProperties: Set the properties of the specified queue. 
- SpecialPermissions: Special permissions for the specified queue. 
- TakeOwnership: Assign the specified queue to oneself.

```yaml
Type: MessageQueueAccessRights
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Deny
Specifies the permissions that are revoked from the supplied user account or group.

The acceptable values for this parameter are:

- Delete: Delete the specified queue. 
FullControl: Full control of the specified queue. 
- GetPermissions: Get the permissions of the specified queue. 
- GetProperties: Get the properties of the specified queue. 
- JournalReceive: Receive a message from the specified queue's journal queue. 
- Peek: Peek a message from the specified queue. 
- Receive: Receive a message from the specified queue. 
- Send: Send a message to the specified queue. 
- SetPermissions: Set the permissions of the specified queue. 
- SetProperties: Set the properties of the specified queue. 
- SpecialPermissions: Special permissions for the specified queue. 
- TakeOwnership: Assign the specified queue to oneself.

```yaml
Type: MessageQueueAccessRights
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies an array of **MsmqQueue** objects that represent the queues for which permissions are updated.
This parameter accepts pipelined input.

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

### -Remove
Specifies the permissions that are removed from the supplied user account or group.

The acceptable values for this parameter are:

- Delete: Delete the specified queue. 
- FullControl: Full control of the specified queue. 
- GetPermissions: Get the permissions of the specified queue. 
- GetProperties: Get the properties of the specified queue. 
- JournalReceive: Receive a message from the specified queue's journal queue. 
- Peek: Peek a message from the specified queue. 
- Receive: Receive a message from the specified queue. 
- Send: Send a message to the specified queue. 
- SetPermissions: Set the permissions of the specified queue. 
- SetProperties: Set the properties of the specified queue. 
- SpecialPermissions: Special permissions for the specified queue. 
- TakeOwnership: Assign the specified queue to oneself.

```yaml
Type: MessageQueueAccessRights
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName
Specifies the user account or group whose permissions are changed.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
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

[Get-MsmqQueueACL](./Get-MsmqQueueACL.md)

