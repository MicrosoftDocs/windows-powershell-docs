---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
Module Name: MSMQ
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/msmq/set-msmqqueuemanageracl?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-MsmqQueueManagerACL
---

# Set-MsmqQueueManagerACL

## SYNOPSIS
Modifies the access rights of a queue manager.

## SYNTAX

```
Set-MsmqQueueManagerACL -UserName <String[]> [-Allow <QueueManagerAccessRights>]
 [-Deny <QueueManagerAccessRights>] [-Remove <QueueManagerAccessRights>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-MsmqQueueManagerACL** cmdlet modifies the access rights of the local queue manager.
This cmdlet returns the updated **MsmqQueueManagerAcl** object.

## EXAMPLES

### Example 1: Modify access rights for the local queue manager
```
PS C:\> Set-MsmqQueueManagerAcl -UserName "CONTOSO\DavidChew" -Allow DeleteMessage,PeekMessage -Deny TakeOwnership,SetPermissions
```

This command modifies the access rights of the local queue manager.

## PARAMETERS

### -Allow
Specifies an array of permissions that this cmdlet grants to a user account or group.
The acceptable values for this parameter are:

- AllExtendedRights.
All extended rights for the specified queue manager.
- CreateChildObjects.
Create child objects with the specified queue manager.
- CreateQueue.
Create a queue with the specified queue manager.
- Delete.
Delete queues of the specified queue manager.
- DeleteChildObjects.
Delete child objects from the specified queue manager.
- FullControl.
Full control of the specified queue manager.
- GetPermissions.
Get the permissions of the specified queue manager.
- GetProperties.
Get the properties of the specified queue manager.
- ListContent.
List content stored in the queues of the specified queue manager.
- PeekDeadLetter.
Peek a message from the specified queue manager system dead letter queue and transactional dead letter queue.
- PeekJournal.
Peek a message from the specified queue manager system journal queue.
- ReceiveDeadLetter.
Receive a message from the specified queue manager system dead letter queue and transactional dead letter queue.
- ReceiveJournal.
Receive a message from the specified queue manager system journal queue.
- SetPermissions.
Set the permissions of the specified queue manager.
- SetProperties.
Set the properties of the specified queue manager.
- TakeOwnership.
Assign a queue of the specified queue manager to oneself.

```yaml
Type: QueueManagerAccessRights
Parameter Sets: (All)
Aliases:
Accepted values: FullControl, CreateQueue, ReceiveDeadLetter, ReceiveComputerJournal, GetProperties, SetProperties, GetPermissions, SetPermissions, TakeOwnership, Delete, PeekDeadLetter, PeekComputerJournal, AllExtendedRights, CreateAllChildObjects, DeleteAllChildObjects, ListObjects

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
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Deny
Specifies an array of permissions that the cmdlet revokes from a user account or group.
The acceptable values for this parameter are:

- AllExtendedRights.
All extended rights for the specified queue manager.
- CreateChildObjects.
Create child objects with the specified queue manager.
- CreateQueue.
Create a queue with the specified queue manager.
- Delete.
Delete queues of the specified queue manager.
- DeleteChildObjects.
Delete child objects from the specified queue manager.
- FullControl.
Full control of the specified queue manager.
- GetPermissions.
Get the permissions of the specified queue manager.
- GetProperties.
Get the properties of the specified queue manager.
- ListContent.
List content stored in the queues of the specified queue manager.
- PeekDeadLetter.
Peek a message from the specified queue manager system dead letter queue and transactional dead letter queue.
- PeekJournal.
Peek a message from the specified queue manager system journal queue.
- ReceiveDeadLetter.
Receive a message from the specified queue manager system dead letter queue and transactional dead letter queue.
- ReceiveJournal.
Receive a message from the specified queue manager system journal queue.
- SetPermissions.
Set the permissions of the specified queue manager.
- SetProperties.
Set the properties of the specified queue manager.
- TakeOwnership.
Assign a queue of the specified queue manager to oneself.

```yaml
Type: QueueManagerAccessRights
Parameter Sets: (All)
Aliases:
Accepted values: FullControl, CreateQueue, ReceiveDeadLetter, ReceiveComputerJournal, GetProperties, SetProperties, GetPermissions, SetPermissions, TakeOwnership, Delete, PeekDeadLetter, PeekComputerJournal, AllExtendedRights, CreateAllChildObjects, DeleteAllChildObjects, ListObjects

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Remove
Specifies an array of permissions that this cmdlet removes from a user account or group.
The acceptable values for this parameter are:

- AllExtendedRights.
All extended rights for the specified queue manager.
- CreateChildObjects.
Create child objects with the specified queue manager.
- CreateQueue.
Create a queue with the specified queue manager.
- Delete.
Delete queues of the specified queue manager.
- DeleteChildObjects.
Delete child objects from the specified queue manager.
- FullControl.
Full control of the specified queue manager.
- GetPermissions.
Get the permissions of the specified queue manager.
- GetProperties.
Get the properties of the specified queue manager.
- ListContent.
List content stored in the queues of the specified queue manager.
- PeekDeadLetter.
Peek a message from the specified queue manager system dead letter queue and transactional dead letter queue.
- PeekJournal.
Peek a message from the specified queue manager system journal queue.
- ReceiveDeadLetter.
Receive a message from the specified queue manager system dead letter queue and transactional dead letter queue.
- ReceiveJournal.
Receive a message from the specified queue manager system journal queue.
- SetPermissions.
Set the permissions of the specified queue manager.
- SetProperties.
Set the properties of the specified queue manager.
- TakeOwnership.
Assign a queue of the specified queue manager to oneself.

```yaml
Type: QueueManagerAccessRights
Parameter Sets: (All)
Aliases:
Accepted values: FullControl, CreateQueue, ReceiveDeadLetter, ReceiveComputerJournal, GetProperties, SetProperties, GetPermissions, SetPermissions, TakeOwnership, Delete, PeekDeadLetter, PeekComputerJournal, AllExtendedRights, CreateAllChildObjects, DeleteAllChildObjects, ListObjects

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName
Specifies the user account or group whose permissions the cmdlet changes.

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

[Get-MsmqQueueManagerACL](./Get-MsmqQueueManagerACL.md)

