---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: Clear-WebRequestTracingSettings
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: D4CBAE62-5E57-4122-9FF8-242C6DA44186
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Clear-WebRequestTracingSettings

## SYNOPSIS
Clears the request tracing configuration from a website.

## SYNTAX

```
Clear-WebRequestTracingSettings [[-Name] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Clear-WebRequestTracingSettings** cmdlet clears request tracing settings from the specified website.
It also disables request tracing for the site.
This cmdlet is identical to Clear-WebRequestTracingSetting, which is preferred.

## EXAMPLES

### Example 1: Removing request tracing from the default web site
```
IIS:\>Clear-WebRequestTracingSettings -Name "Default Web Site"
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

[Clear-WebRequestTracingSetting](./Clear-WebRequestTracingSetting.md)

