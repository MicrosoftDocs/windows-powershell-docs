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
title: Set-MsmqQueueACL
ms.reviewer:
ms.assetid: 4DAF0FE1-6D1E-4F47-8441-78DEFDB24512
---

# Set-MsmqQueueACL

## SYNOPSIS
Modifies the access rights of queues.

## SYNTAX

```
Set-MsmqQueueACL [-InputObject] <MessageQueue[]> -UserName <String[]> [-Allow <MessageQueueAccessRights>]
 [-Deny <MessageQueueAccessRights>] [-Remove <MessageQueueAccessRights>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-MsmqQueueACL** cmdlet modifies the access rights of queues.
This cmdlet returns the updated **MsmqQueueAcl** object.
The cmdlet modifies private, public, journal, system journal, system dead-letter, and system transactional dead-letter queues.

## EXAMPLES

### Example 1: Modify the ACLs of queues specified by name
```
PS C:\> Get-MsmqQueue -Name "Order*" -QueueType Private | Set-MsmqQueueAcl -UserName "CONTOSO\DavidChew" -Allow Delete,Peek,Receive,Send -Deny TakeOwnership
```

This command gets all the private queues that have names that start with the string Order by using the **Get-MsmqQueue** cmdlet.
The command passes the results to the current cmdlet by using the pipeline operator.
The current cmdlet modifies the ACL of the queues.

## PARAMETERS

### -Allow
Specifies an array of permissions that this cmdlet grants to a user account or group.
The acceptable values for this parameter are:

- Delete.
Delete the specified queue. 
- FullControl.
Full control of the specified queue. 
- GetPermissions.
Get the permissions of the specified queue. 
- GetProperties.
Get the properties of the specified queue. 
- JournalReceive.
Receive a message from the specified queue journal queue. 
- Peek.
Peek a message from the specified queue. 
- Receive.
Receive a message from the specified queue. 
- Send.
Send a message to the specified queue. 
- SetPermissions.
Set the permissions of the specified queue. 
- SetProperties.
Set the properties of the specified queue. 
- SpecialPermissions.
Special permissions for the specified queue. 
- TakeOwnership.
Assign the specified queue to oneself.

```yaml
Type: MessageQueueAccessRights
Parameter Sets: (All)
Aliases: 
Accepted values: DeleteMessage, PeekMessage, ReceiveMessage, WriteMessage, DeleteJournalMessage, ReceiveJournalMessage, SetQueueProperties, GetQueueProperties, DeleteQueue, GetQueuePermissions, GenericWrite, GenericRead, ChangeQueuePermissions, TakeQueueOwnership, FullControl

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

- Delete.
Delete the specified queue. 
- FullControl.
Full control of the specified queue. 
- GetPermissions.
Get the permissions of the specified queue. 
- GetProperties.
Get the properties of the specified queue. 
- JournalReceive.
Receive a message from the specified queue journal queue. 
- Peek.
Peek a message from the specified queue. 
- Receive.
Receive a message from the specified queue. 
- Send.
Send a message to the specified queue. 
- SetPermissions.
Set the permissions of the specified queue. 
- SetProperties.
Set the properties of the specified queue. 
- SpecialPermissions.
Special permissions for the specified queue. 
- TakeOwnership.
Assign the specified queue to oneself.

```yaml
Type: MessageQueueAccessRights
Parameter Sets: (All)
Aliases: 
Accepted values: DeleteMessage, PeekMessage, ReceiveMessage, WriteMessage, DeleteJournalMessage, ReceiveJournalMessage, SetQueueProperties, GetQueueProperties, DeleteQueue, GetQueuePermissions, GenericWrite, GenericRead, ChangeQueuePermissions, TakeQueueOwnership, FullControl

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies an array of **MsmqQueue** objects.
This cmdlet updates permissions for the queues that the **MsmqQueue** objects specify.
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

### -Remove
Specifies an array of permissions that this cmdlet removes from a user account or group.
The acceptable values for this parameter are:

- Delete.
Delete the specified queue. 
- FullControl.
Full control of the specified queue. 
- GetPermissions.
Get the permissions of the specified queue. 
- GetProperties.
Get the properties of the specified queue. 
- JournalReceive.
Receive a message from the specified queue journal queue. 
- Peek.
Peek a message from the specified queue. 
- Receive.
Receive a message from the specified queue. 
- Send.
Send a message to the specified queue. 
- SetPermissions.
Set the permissions of the specified queue. 
- SetProperties.
Set the properties of the specified queue. 
- SpecialPermissions.
Special permissions for the specified queue. 
- TakeOwnership.
Assign the specified queue to oneself.

```yaml
Type: MessageQueueAccessRights
Parameter Sets: (All)
Aliases: 
Accepted values: DeleteMessage, PeekMessage, ReceiveMessage, WriteMessage, DeleteJournalMessage, ReceiveJournalMessage, SetQueueProperties, GetQueueProperties, DeleteQueue, GetQueuePermissions, GenericWrite, GenericRead, ChangeQueuePermissions, TakeQueueOwnership, FullControl

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-MsmqQueue](./Get-MsmqQueue.md)

[Get-MsmqQueueACL](./Get-MsmqQueueACL.md)

