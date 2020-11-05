---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: Restart-WebAppPool
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: DF86D4F3-5727-4E04-9A4C-474D8A1F66CC
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Restart-WebAppPool

## SYNOPSIS
Restarts an application pool.

## SYNTAX

```
Restart-WebAppPool [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Restart-WebAppPool** cmdlet restarts the specified application pool.

## EXAMPLES

### Example 1: Restart an application pool
```
IIS:\>Restart-WebAppPool -Name "DefaultAppPool"
```

This command restarts the application pool named DefaultAppPool.

## PARAMETERS

### -Name
Specifies the name of the application pool to restart.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-WebAppPool](./New-WebAppPool.md)

[Remove-WebAppPool](./Remove-WebAppPool.md)

[Start-WebAppPool](./Start-WebAppPool.md)

[Stop-WebAppPool](./Stop-WebAppPool.md)

