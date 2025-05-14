---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipoint/get-wmssession?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WmsSession
---

# Get-WmsSession

## SYNOPSIS
Gets session information.

## SYNTAX

### GetById
```
Get-WmsSession [-SessionId] <UInt32[]> [-Thumbnail <ThumbnailSizePS>] [-Server <String>] [<CommonParameters>]
```

### GetAll
```
Get-WmsSession [-All] [-Thumbnail <ThumbnailSizePS>] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WmsSession** cmdlet gets information for a specified session or for all sessions.

## EXAMPLES

### Example 1: Get all sessions
```
PS C:\> Get-WmsSession -All
SessionId    : 2
State        : RemoteConnection
IsOrchestratable    : False
IsAdmin      : True
IsMOGUser    : True
UserName     : Test
StationId    : 0
ComputerName : Test1
ClientName   : Test2
DomainName   : TestDomain
IsRail       : False
SessionId    : 3
State        : ConnectedToStation
IsOrchestratable    : False
IsAdmin      : True
IsMOGUser    : True
UserName     : Administrator
StationId    : 1
ComputerName : Test1
ClientName   : Test1
DomainName   : TestDomain
IsRail       : False
```

This command gets session information for all sessions.
The session with ID 2 is a remote session, and the session with ID 3 is a session connected to a local Windows MultiPoint Server station.


## PARAMETERS

### -All
Indicates that this operation applies to all sessions on the target host.

```yaml
Type: SwitchParameter
Parameter Sets: GetAll
Aliases:

Required: True
Position: Named
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
Parameter Sets: GetById
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Thumbnail
Specifies the Thumbnail size of the session.

```yaml
Type: ThumbnailSizePS
Parameter Sets: (All)
Aliases:
Accepted values: Small, Medium, Large, FullScreen

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.UInt32[]

### System.String

## OUTPUTS

### Microsoft.WindowsServerSolutions.MultipointServer.PowerShell.Commands.Library.WmsSession

## NOTES

## RELATED LINKS

[Close-WmsSession](./Close-WmsSession.md)

[Disconnect-WmsSession](./Disconnect-WmsSession.md)

[Lock-WmsSession](./Lock-WmsSession.md)

[Unlock-WmsSession](./Unlock-WmsSession.md)

