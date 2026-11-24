---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipoint/show-wmsdesktop?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Show-WmsDesktop
---

# Show-WmsDesktop

## SYNOPSIS
Displays the currently shared desktop to the specified sessions.

## SYNTAX

### ShowSessionList
```
Show-WmsDesktop [-SessionId] <UInt32[]> -Desktop <WmsDesktop> [-Server <String>] [<CommonParameters>]
```

### ShowAll
```
Show-WmsDesktop [-All] -Desktop <WmsDesktop> [-Server <String>] [<CommonParameters>]
```

### RemoteControl
```
Show-WmsDesktop -Desktop <WmsDesktop> [-Title <String>] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Show-WmsDesktop** cmdlet displays the currently shared desktop to the specified sessions on the current Windows MultiPoint Server system.

## EXAMPLES

### Example 1: Show a desktop
```
PS C:\> Show-WmsDesktop -Invitation "See My Shared Desktop" -SessionId "1,2" -Title "Teacher's Desktop"
```

This command projects the desktop to the specified session list.

## PARAMETERS

### -All
Indicates that this operation applies to all sessions on the target host.

```yaml
Type: SwitchParameter
Parameter Sets: ShowAll
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Desktop
{{Fill Desktop Description}}

```yaml
Type: WmsDesktop
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
Parameter Sets: ShowSessionList
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Title
Specifies a title.

```yaml
Type: String
Parameter Sets: RemoteControl
Aliases:

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

### Microsoft.WindowsServerSolutions.MultipointServer.PowerShell.Commands.Library.WmsDesktop

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Unpublish-WmsDesktop](./Unpublish-WmsDesktop.md)

[Publish-WmsDesktop](./Publish-WmsDesktop.md)

