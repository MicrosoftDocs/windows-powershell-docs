---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/invoke-rduserlogoff?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-RDUserLogoff
---

# Invoke-RDUserLogoff

## SYNOPSIS
Ends a user session and closes all running applications.

## SYNTAX

```
Invoke-RDUserLogoff [-HostServer] <String> [-UnifiedSessionID] <Int32> [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Invoke-RDUserLogoff** cmdlet ends a user session and closes any running applications.

To end a session without closing applications use the Disconnect-RDUser cmdlet.

To get the ID for the user session that you are ending, use the Get-RDUserSession cmdlet.
Because the user session ID is unique only within the context of a session host, a different session within a deploymenthost server can share the same user session ID.
The host server and session ID that you specify in this cmdlet uniquely identify a session within a deployment.

## EXAMPLES

### Example 1: End a session connected to an RD Session Host server
```
PS C:\> Invoke-RDUserLogoff -HostServer "rdsh-1.contoso.com" -UnifiedSessionID 2
```

This command ends the user session that has the ID 2, which is connected to the host server named rdsh-1.contoso.com.

### Example 2: End a session connected to an RD Virtualization Host server
```
PS C:\> Invoke-RDUserLogoff -HostServer "rdvh-1.contoso.com" -UnifiedSessionID 14 -Force
```

This command ends the user session that has the ID 14, which is connected to the virtualization host server named rdvh-1.contoso.com.
Because the command includes the **Force** parameter, it ends the session without prompting for user confirmation.

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
Specifies a unique session ID on the host.
Use Get-RDUserSession to retrieve the unique ID for a specific user session.

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

[Send-RDUserMessage](./Send-RDUserMessage.md)

