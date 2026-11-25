---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/send-rdusermessage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Send-RDUserMessage
---

# Send-RDUserMessage

## SYNOPSIS
Sends a system message to a specified user session.

## SYNTAX

```
Send-RDUserMessage [-HostServer] <String> [-UnifiedSessionID] <Int32> [-MessageTitle] <String>
 [-MessageBody] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Send-RDUserMessage** cmdlet sends a system message to a specified user session.
Because the user session ID is unique only within the context of a session host, a different session host server can share the same user session ID.
The host server and session ID that you specify by using this cmdlet uniquely identify a session within a deployment.

## EXAMPLES

### Example 1: Send a system message to users of a Remote Desktop application
```
PS C:\> Send-RDUserMessage -HostServer "rdsh.contoso.com" -UnifiedSessionID 1 -MessageTitle "Message from Administrator" -MessageBody "Please save your work. You will be logged off in 10 minutes"
```

This command sends a system message to users of the session with an ID of 1 on the host server named rdsh.contoso.com.

## PARAMETERS

### -HostServer
Specifies the name of the server that hosts the session.
For session collections the host server has the name of the Remote Desktop Session Host (RD  Session Host) server.
For virtual desktop collections the host server has the name of the Remote Desktop Virtualization Host (RD Virtualization Host) server.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MessageBody
Specifies the text for the message body.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MessageTitle
Specifies the text for the message title.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UnifiedSessionID
Specifies a unique session ID on the host.
Use Get-RDUserSession to retrieve the unique ID for a specific session.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Disconnect-RDUser](./Disconnect-RDUser.md)

[Get-RDUserSession](./Get-RDUserSession.md)

[Invoke-RDUserLogoff](./Invoke-RDUserLogoff.md)

