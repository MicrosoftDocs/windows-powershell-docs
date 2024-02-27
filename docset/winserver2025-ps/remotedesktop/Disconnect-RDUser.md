---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/disconnect-rduser?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disconnect-RDUser
---

# Disconnect-RDUser

## SYNOPSIS
Disconnects a user from a session that runs on a remote server.

## SYNTAX

```
Disconnect-RDUser [-HostServer] <String> [-UnifiedSessionID] <Int32> [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Disconnect-RDUser** cmdlet disconnects a specified user from a session that runs on the remote server.
All applications continue to run.

Use the Invoke-RDUserLogoff cmdlet to end a session and close running applications.

Use the Get-RDUserSessioncmdlet to retrieve the value for the user session ID.
Because the user session ID is unique only within the context of a session host, a different session host server can share the same user session ID.
The host server and session ID that you specify in this cmdlet uniquely identify a session within a deployment.

## EXAMPLES

### Example 1: Disconnect a User from a session on an RD Session Host Server
```
PS C:\> Disconnect-RDUser -HostServer sessionhost.contoso.com -UnifiedSessionID 2
```

This command disconnects the user connected to session 2 on the host server sessionhost.contoso.com.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.

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

### -HostServer
Specifies the name of the server that hosts the session.
For session collections the server name is the name of the Remote Desktop Session Host (RD Session Host) server.
For virtual desktop collections the server name is the name of the Remote Desktop Virtualization Host (RD Virtualization Host) server.

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

### -UnifiedSessionID
Provides the unique ID for the session.
Use the Get-RDUserSession cmdlet to retrieve the user session ID.

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

[Get-RDUserSession](./Get-RDUserSession.md)

[Invoke-RDUserLogoff](./Invoke-RDUserLogoff.md)

[Send-RDUserMessage](./Send-RDUserMessage.md)

