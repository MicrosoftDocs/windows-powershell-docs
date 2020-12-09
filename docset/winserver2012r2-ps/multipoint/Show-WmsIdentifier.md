---
external help file: WmsCmdlets.dll-Help.xml
Module Name: WmsCmdlets
online version: 
schema: 2.0.0
title: Show-WmsIdentifier
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/06/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: C281BBA8-F498-4A9B-8D88-1143EEEBFEF7
ms.reviewer:
ms.author: v-kaunu
---

# Show-WmsIdentifier

## SYNOPSIS
Displays identification screen.

## SYNTAX

```
Show-WmsIdentifier [-SessionId <UInt32>] [-StationId <UInt32>] [-TimeoutInSecond <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The Show-WmsIdentifier displays the identification screen for the specified station.
The top line shown is the client name.
For a Windows MultiPoint Server station, the station-friendly name is used as the client name.
The bottom name is the system in which this session is hosted.

## EXAMPLES

### Example
```
PS C:\> Show-WmsIdentifier -SessionId 2 PS C:\> Show-WmsIdentifier -StationId 1
No output.
```

The identification screen for the specified session will be displayed.
The first line displays the system which runs the remote-desktop client and the second line displays the system that is hosting the session. 
The identification screen for the specified MultiPoint Server station will be displayed.
The first line displays the station friendly name for the specified station and the second line displays the local server name.

### 1:
```
PS C:\>
```

## PARAMETERS

### -SessionId
Specifies a Remote Desktop Session (RDS) using SessionID.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -StationId
Specifies a Windows MultiPoint Server station.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutInSecond
The timeout value in seconds before the operation is aborted.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

