---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipoint/lock-wmssession?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Lock-WmsSession
---

# Lock-WmsSession

## SYNOPSIS
Locks a session for a user.

## SYNTAX

### LockById
```
Lock-WmsSession [-SessionId] <UInt32[]> [-Message] <String> [-Server <String>] [<CommonParameters>]
```

### LockAll
```
Lock-WmsSession [-All] [-Message] <String> [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Lock-WmsSession** cmdlet blocks desktop use for a specific user.
You can specify a message to display on the user's screen.

## EXAMPLES

### Example 1: Lock a session
```
PS C:\> Lock-WmsSession -SessionId 3 -Message "Your station is locked"
```

This command locks the specified session and displays the message "Your station is locked" to the user.

## PARAMETERS

### -All
Indicates that this operation applies to all sessions on the target host.

```yaml
Type: SwitchParameter
Parameter Sets: LockAll
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Message
Specifies the message to display.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
Specifies the fully qualified host name of the MultiPoint Server that is the target of the command.
The default is localhost.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ComputerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SessionId
Specifies an array of session IDs.

```yaml
Type: UInt32[]
Parameter Sets: LockById
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.UInt32[]

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Close-WmsSession](./Close-WmsSession.md)

[Disconnect-WmsSession](./Disconnect-WmsSession.md)

[Get-WmsSession](./Get-WmsSession.md)

[Unlock-WmsSession](./Unlock-WmsSession.md)

