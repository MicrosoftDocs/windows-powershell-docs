---
external help file: WmsCmdlets.dll-Help.xml
Module Name: WmsCmdlets
online version: 
schema: 2.0.0
title: Lock-WmsSession
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/06/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: B4D13723-44A5-455A-97A8-88C4C46523E7
ms.reviewer:
ms.author: v-kaunu
---

# Lock-WmsSession

## SYNOPSIS
Blocks desktop use for a specific user.

## SYNTAX

```
Lock-WmsSession -SessionId <UInt32> -LockMessage <String> [-TimeoutInSecond <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The Lock-WmsSession cmdlet blocks desktop use for a specific user.
You can specify a message to be displayed on the user's screen.

## EXAMPLES

### Example 1:
```
PS C:\> [System.Convert]::ToBase64String([System.Text.Encoding]::UNICODE.GetBytes("Your station is locked")) | Write-Output WQBvAHUAcgAgAHMAdABhAHQAaQBvAG4AIABpAHMAIABsAG8AYwBrAGUAZAA=

PS C:\> Lock-WmsSession -SessionId 3 -LockMessage WQBvAHUAcgAgAHMAdABhAHQAaQBvAG4AIABpAHMAIABsAG8AYwBrAGUAZAA=
No output.
```

The station is locked, and the screen shows the message, "Your station is locked".

## PARAMETERS

### -LockMessage
The message to be displayed on the user's screen.

This parameter is BASE64 encoded.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

