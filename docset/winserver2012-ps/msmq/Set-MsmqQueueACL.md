---
external help file: MSMQ_Cmdlets.xml
Module Name: MSMQ
online version: https://learn.microsoft.com/powershell/module/msmq/set-msmqqueueacl?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
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

### Example 1: Modify the ACLs of queues specified by name
```powershell
PS C:\> $queue = Get-MsmqQueue -Name "Order*" -QueueType Private
PS C:\> $rights = "DeleteQueue", "PeekMessage", "ReceiveMessage", "WriteMessage"
PS C:\> $rights | Foreach-Object { Set-MsmqQueueAcl -InputObject $queue -UserName "CONTOSO\DavidChew" -Allow $PSItem}
PS C:\> Set-MsmqQueueAcl -InputObject $queue -UserName "CONTOSO\DavidChew" -Deny TakeQueueOwnership
```

This command gets all the private queues that have names that start with the string Order by using the **Get-MsmqQueue** cmdlet. The current cmdlet modifies the ACL of the queues.

## PARAMETERS

### -Allow
Specifies the permissions that are granted to the supplied user account or group.

The acceptable values for this parameter are:

- DeleteQueue - Delete the specified queue
- FullControl - Full control of the specified queue
- GetQueuePermissions - Get the permissions of the specified queue
- GetQueueProperties - Get the properties of the specified queue 
- ReceiveJournalMessage - Receive messages from the journal queue. This includes the rights to delete and peek messages from the journal queue
- DeleteJournalMessage - Delete messages from the journal queue
- PeekMessage - Peek a message from the specified queue
- ReceiveMessage - Receive messages from the queue. This includes the rights to delete and peek messages
- WriteMessage - Send a message to the specified queue
- DeleteMessage - Delete a message from the specified queue
- ChangeQueuePermissions - Set the permissions of the specified queue
- SetQueueProperties - Set the properties of the specified queue
- TakeQueueOwnership - Assign the specified queue to oneself
- GenericRead - A combination of `GetQueueProperties`, `GetQueuePermissions`, `ReceiveMessage`, and `ReceiveJournalMessage`
- GenericWrite - A combination of `GetQueueProperties`, `GetQueuePermissions`, and `WriteMessage`

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

- DeleteQueue - Delete the specified queue
- FullControl - Full control of the specified queue
- GetQueuePermissions - Get the permissions of the specified queue
- GetQueueProperties - Get the properties of the specified queue 
- ReceiveJournalMessage - Receive messages from the journal queue. This includes the rights to delete and peek messages from the journal queue
- DeleteJournalMessage - Delete messages from the journal queue
- PeekMessage - Peek a message from the specified queue
- ReceiveMessage - Receive messages from the queue. This includes the rights to delete and peek messages
- WriteMessage - Send a message to the specified queue
- DeleteMessage - Delete a message from the specified queue
- ChangeQueuePermissions - Set the permissions of the specified queue
- SetQueueProperties - Set the properties of the specified queue
- TakeQueueOwnership - Assign the specified queue to oneself
- GenericRead - A combination of `GetQueueProperties`, `GetQueuePermissions`, `ReceiveMessage`, and `ReceiveJournalMessage`
- GenericWrite - A combination of `GetQueueProperties`, `GetQueuePermissions`, and `WriteMessage`

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

- DeleteQueue - Delete the specified queue
- FullControl - Full control of the specified queue
- GetQueuePermissions - Get the permissions of the specified queue
- GetQueueProperties - Get the properties of the specified queue 
- ReceiveJournalMessage - Receive messages from the journal queue. This includes the rights to delete and peek messages from the journal queue
- DeleteJournalMessage - Delete messages from the journal queue
- PeekMessage - Peek a message from the specified queue
- ReceiveMessage - Receive messages from the queue. This includes the rights to delete and peek messages
- WriteMessage - Send a message to the specified queue
- DeleteMessage - Delete a message from the specified queue
- ChangeQueuePermissions - Set the permissions of the specified queue
- SetQueueProperties - Set the properties of the specified queue
- TakeQueueOwnership - Assign the specified queue to oneself
- GenericRead - A combination of `GetQueueProperties`, `GetQueuePermissions`, `ReceiveMessage`, and `ReceiveJournalMessage`
- GenericWrite - A combination of `GetQueueProperties`, `GetQueuePermissions`, and `WriteMessage`

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

