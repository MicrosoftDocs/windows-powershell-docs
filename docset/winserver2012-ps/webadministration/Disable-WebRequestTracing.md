---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: https://learn.microsoft.com/powershell/module/webadministration/disable-webrequesttracing?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Disable-WebRequestTracing

## SYNOPSIS
Disables Request Tracing for the specified site.

## SYNTAX

```
Disable-WebRequestTracing [[-Name] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Disables Request Tracing for the specified site, but does not remove Request Tracing settings.

## EXAMPLES

### -------------- EXAMPLE 1: Disabling Request Tracing for the "Default Web Site" --------------
```
IIS:\>Disable-WebRequestTracing -Name "Default Web Site"
```

Disables Request Tracing for the Default Web Site.

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
The name of site for which Request Tracing is disabled.

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
* Request Tracing settings can be removed by using theT:Microsoft.IIs.PowerShell.Provider.Clear-WebRequestTracingSettingscmdlet.

## RELATED LINKS

[Enable-WebRequestTracing](./Enable-WebRequestTracing.md)

