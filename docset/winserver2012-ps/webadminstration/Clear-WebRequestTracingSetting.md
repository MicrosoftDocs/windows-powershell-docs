---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: B03DC350-FFFE-442B-942C-FF180D5370A2
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Clear-WebRequestTracingSetting

## SYNOPSIS
Clears the Request Tracing configuration from the specified Web site.

## SYNTAX

```
Clear-WebRequestTracingSetting [[-Name] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Clears Request Tracing settings from the specified Web site.
It also disables Request Tracing for the site.
This command is identical to Clear-WebRequestTracingSettings.

## EXAMPLES

### -------------- EXAMPLE 1: Removing Request Tracing from the Default Web Site --------------
```
IIS:\>Clear-WebRequestTracingSettings -Name "Default Web Site"
```

Demonstrates how to remove Request Tracing from the Default Web Site.

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
The name of the site from which Request Trace settings are cleared.

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

