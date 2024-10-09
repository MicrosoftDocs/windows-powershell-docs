---
external help file: WinHttpProxy-help.xml
Module Name: WinHttpProxy
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/winhttpproxy/set-winhttpproxy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WinhttpProxy
---

# Set-WinhttpProxy

## SYNOPSIS
Configures WinHTTP proxy settings.

## SYNTAX

### Default

```
Set-WinhttpProxy [-ProxyServer] <String> [[-BypassList] <String>] [<CommonParameters>]
```

### Advanced

```
Set-WinhttpProxy [-SettingScope] <String> [-Proxy <String>] [-ProxyBypass <String>] [-AutoconfigUrl <String>]
 [-AutoDetect] [<CommonParameters>]
```

## DESCRIPTION

Configures WinHTTP proxy settings.

## EXAMPLES

### Example 1

```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -AutoconfigUrl

{{ Fill AutoconfigUrl Description }}

```yaml
Type: System.String
Parameter Sets: Advanced
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutoDetect

{{ Fill AutoDetect Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Advanced
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -BypassList

{{ Fill BypassList Description }}

```yaml
Type: System.String
Parameter Sets: Default
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Proxy

{{ Fill Proxy Description }}

```yaml
Type: System.String
Parameter Sets: Advanced
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyBypass

{{ Fill ProxyBypass Description }}

```yaml
Type: System.String
Parameter Sets: Advanced
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyServer

{{ Fill ProxyServer Description }}

```yaml
Type: System.String
Parameter Sets: Default
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SettingScope

{{ Fill SettingScope Description }}

```yaml
Type: System.String
Parameter Sets: Advanced
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
