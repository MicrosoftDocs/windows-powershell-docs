---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: Clear-WebRequestTracingSetting
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: B03DC350-FFFE-442B-942C-FF180D5370A2
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Clear-WebRequestTracingSetting

## SYNOPSIS
Clears the request tracing configuration from a website.

## SYNTAX

```
Clear-WebRequestTracingSetting [[-Name] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Clear-WebRequestTracingSetting** cmdlet clears request tracing settings from the specified website.
It also disables request tracing for the site.
This cmdlet is identical to Clear-WebRequestTracingSettings.

## EXAMPLES

### Example 1: Removing request tracing from the default web site
```
IIS:\>Clear-WebRequestTracingSetting -Name "Default Web Site"
```

This command removes request tracing from the default website.

## PARAMETERS

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

### -Name
Specifies the name of the site from which request tracing settings are cleared.

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-WebRequestTracing](./Disable-WebRequestTracing.md)

[Clear-WebRequestTracingSettings](./Clear-WebRequestTracingSettings.md)

