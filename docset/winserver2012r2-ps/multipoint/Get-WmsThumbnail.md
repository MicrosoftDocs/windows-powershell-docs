---
external help file: WmsCmdlets.dll-Help.xml
Module Name: WmsCmdlets
online version: 
schema: 2.0.0
title: Get-WmsThumbnail
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/06/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: AE3B8DB9-C081-48CE-A1D1-43BA7244F329
ms.reviewer:
ms.author: v-kaunu
---

# Get-WmsThumbnail

## SYNOPSIS
Returns a screen shot of the specified session.

## SYNTAX

```
Get-WmsThumbnail [-SerializeString] -SessionId <UInt32> -BitmapSize <UInt32> [-TimeoutInSecond <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Get-WmsThumbnail cmdlet returns a screen shot of the specified session based on the requested size.

## EXAMPLES

### Example
```
PS C:\> Get-WmsThumbnail -SessionId 3 -BitmapSize 1
CurrentApplication   : Program Manager

IdleTimespan         : 66515

Blanked              : False

BlankedMessage       : 

IsLocked             : False

IsDisconnected       : False

IsPrivate            : False

IsBitmapUnavailable  : False

ScreenBroadcastState : Quiescent

RemoteControlState   : Quiescent

WebLimitingState     : NotLimited

ThumbnailBits        : {255, 216, 255, 224...}
```

Returns a snapshot of the current desktop of the specified session.BitmapSize can be any value between 0 & 3, with 0 for the smallest size and 4 for full screen.
Along with screenshot information, this cmdlet also returns the current state of the specified session.

### 1:
```
PS C:\>
```

## PARAMETERS

### -BitmapSize
Returns the thumbnail image based on the specified size.
It can be a number between 0 and 3, with 0 being the smallest size and 3 for the largest size.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SerializeString
Returns data in XML format.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SessionId
Specifies a Remote Desktop Session (RDS) using SessionID.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Describes what would happen if you executed the command without actually executing the command.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

###  
Returns WmsSessionStatus collection as PSObject collection.

## NOTES

## RELATED LINKS

