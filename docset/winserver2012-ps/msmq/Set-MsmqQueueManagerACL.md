---
external help file: MSMQ_Cmdlets.xml
Module Name: MSMQ
online version: https://learn.microsoft.com/powershell/module/msmq/set-msmqqueuemanageracl?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-MsmqQueueManagerACL

## SYNOPSIS
Sets access rights of the local queue manager.

## SYNTAX

```
Set-MsmqQueueManagerACL [-Allow <QueueManagerAccessRights>] [-Deny <QueueManagerAccessRights>]
 [-Remove <QueueManagerAccessRights>] -UserName <String[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-MsmqQueueManagerACL** cmdlet sets the access rights of the local queue manager.
This cmdlet returns the updated **MsmqQueueManagerAcl** object.

## EXAMPLES

### Example 1: Set the access rights of the local queue manager
```
PS C:\>Set-MsmqQueueManagerAcl -UserName "CONTOSO\pattiful" -Allow DeleteMessage,PeekMessage -Deny TakeOwnership,SetPermissions
```

This command sets the access rights to Allow, DeleteMessage, and PeekMessage for the user named CONTOSO\pattiful on the default queue.
This command also allows the user to take ownership and set permissions on that queue.

## PARAMETERS

### -Allow
Specifies the permissions that are granted to the supplied user account or group.

The acceptable values for this parameter are:

- AllExtendedRights: All extended rights for the specified queue manager. 
- CreateChildObjects: Create child objects with the specified queue manager. 
- CreateQueue: Create a queue with the specified queue manager. 
- Delete: Delete queues of the specified queue manager. 
- DeleteChildObjects: Delete child objects from the specified queue manager. 
- FullControl: Full control of the specified queue manager. 
- GetPermissions: Get the permissions of the specified queue manager. 
- GetProperties: Get the properties of the specified queue manager. 
ListContent: List content stored in the queues of the specified queue manager. 
- PeekDeadLetter: Peek a message from the specified queue manager's system dead letter queue and transactional dead letter queue. 
- PeekJournal: Peek a message from the specified queue manager's system journal queue. 
- ReceiveDeadLetter: Receive a message from the specified queue manager's system dead letter queue and transactional dead letter queue. 
- ReceiveJournal: Receive a message from the specified queue manager's system journal queue. 
- SetPermissions: Set the permissions of the specified queue manager. 
- SetProperties: Set the properties of the specified queue manager. 
- TakeOwnership: Assign a queue of the specified queue manager to the specified user.

```yaml
Type: QueueManagerAccessRights
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

- AllExtendedRights: All extended rights for the specified queue manager. 
- CreateChildObjects: Create child objects with the specified queue manager. 
- CreateQueue: Create a queue with the specified queue manager. 
- Delete: Delete queues of the specified queue manager. 
- DeleteChildObjects: Delete child objects from the specified queue manager. 
- FullControl: Full control of the specified queue manager. 
- GetPermissions: Get the permissions of the specified queue manager. 
- GetProperties: Get the properties of the specified queue manager. 
- ListContent: List content stored in the queues of the specified queue manager. 
- PeekDeadLetter: Peek a message from the specified queue manager's system dead letter queue and transactional dead letter queue. 
- PeekJournal: Peek a message from the specified queue manager's system journal queue. 
- ReceiveDeadLetter: Receive a message from the specified queue manager's system dead letter queue and transactional dead letter queue. 
- ReceiveJournal: Receive a message from the specified queue manager's system journal queue. 
- SetPermissions: Set the permissions of the specified queue manager. 
- SetProperties: Set the properties of the specified queue manager. 
- TakeOwnership: Assign a queue of the specified queue manager to the user.

```yaml
Type: QueueManagerAccessRights
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Remove
```yaml
Type: QueueManagerAccessRights
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName
Specifies the user account or group whose permissions are to be changed.

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

[Get-MsmqQueueManagerACL](./Get-MsmqQueueManagerACL.md)

