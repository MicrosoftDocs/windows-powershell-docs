---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: Disable-WebRequestTracing
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 7DA8AEFC-8965-437B-8720-4DC6B702A825
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Disable-WebRequestTracing

## SYNOPSIS
Disables request tracing for a website.

## SYNTAX

```
Disable-WebRequestTracing [[-Name] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-WebRequestTracing** cmdlet disables request tracing for the specified website, but does not remove request tracing settings.

## EXAMPLES

### Example 1: Disabling request tracing for the "Default Web Site"
```
IIS:\>Disable-WebRequestTracing -Name "Default Web Site"
```

This command disables request tracing for the default website.

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
Specifies the name of site for which request tracing is disabled.

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
* You can use the Clear-WebRequestTracingSetting cmdlet to remove request tracing settings.

## RELATED LINKS

[Clear-WebRequestTracingSetting](./Clear-WebRequestTracingSetting.md)

[Enable-WebRequestTracing](./Enable-WebRequestTracing.md)

