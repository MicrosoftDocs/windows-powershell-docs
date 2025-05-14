---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipoint/enable-wmsweblimiting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WmsWebLimiting
---

# Enable-WmsWebLimiting

## SYNOPSIS
Enables web limiting for a session.

## SYNTAX

### WebLimitSession
```
Enable-WmsWebLimiting [-SessionId] <UInt32[]> [-Server <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### WebLimitAll
```
Enable-WmsWebLimiting [-All] [-Server <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-WmsWebLimiting** cmdlet enables web limiting for the specified sessions.

## EXAMPLES

### Example 1: Enable web limiting for a session
```
PS C:\> Enable-WmsWebLimiting -SessionId 2
```

This command enables web access restrictions for session 2 on the local computer.

### Example 2: Enable web limiting for all sessions
```
PS C:\> Enable-WmsWebLimiting -Server "Sample.microsoft.com" -All
```

This command enables web access restrictions for all sessions on the computer Sample.microsoft.com.

## PARAMETERS

### -All
Indicates that this operation applies to all sessions on the target host.

```yaml
Type: SwitchParameter
Parameter Sets: WebLimitAll
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
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
Specifies the fully qualified host name of the MultiPoint system that is the target of the command.
The parameter is optional and if omitted defaults to localhost.

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
Specifies an array of MultiPoint session IDs that are the target of the command.

```yaml
Type: UInt32[]
Parameter Sets: WebLimitSession
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System.UInt32[]

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Disable-WmsWebLimiting](./Disable-WmsWebLimiting.md)

[Get-WmsWebLimiting](./Get-WmsWebLimiting.md)

[Set-WmsWebLimiting](./Set-WmsWebLimiting.md)

