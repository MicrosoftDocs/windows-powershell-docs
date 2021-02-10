---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Unpublish-WmsDesktop
ms.reviewer:
ms.assetid: A68E5031-A7D9-43BC-90E5-5ACD5714E7C7
---

# Unpublish-WmsDesktop

## SYNOPSIS
Stops the sharing of the specified session desktop.

## SYNTAX

```
Unpublish-WmsDesktop [-SessionId] <UInt32> [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Unpublish-WmsDesktop** cmdlet stops the sharing of the specified session desktop.

## EXAMPLES

### Example 1: Stop sharing a desktop
```
PS C:\> Unpublish-WmsDesktop -SessionId 2
```

This command stops desktop sharing of the desktop with the session ID of 2.

## PARAMETERS

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
Specifies the session ID to stop sharing.

```yaml
Type: UInt32
Parameter Sets: (All)
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

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Publish-WmsDesktop](./Publish-WmsDesktop.md)

[Show-WmsDesktop](./Show-WmsDesktop.md)

