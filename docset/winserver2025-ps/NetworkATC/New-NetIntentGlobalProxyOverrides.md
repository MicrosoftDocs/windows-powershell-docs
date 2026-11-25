---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 03/14/2025
online version: https://learn.microsoft.com/powershell/module/networkatc/new-netintentglobalproxyoverrides?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetIntentGlobalProxyOverrides
---

# New-NetIntentGlobalProxyOverrides

## SYNOPSIS
Creates a new instance for global proxy overrides.

## SYNTAX

### Default (Default)

```
New-NetIntentGlobalProxyOverrides -ProxyServer <String> [-ProxyBypass <String>] [-AutoDetect]
 [<CommonParameters>]
```

### AutoDetect

```
New-NetIntentGlobalProxyOverrides [-AutoDetect] -AutoConfigUrl <String> [<CommonParameters>]
```

## DESCRIPTION

The `New-NetIntentGlobalProxyOverrides` cmdlet configures proxy setting override by specifying a
proxy server or bypass list.

## EXAMPLES

### Example

```powershell
$params = @{
    ProxyServer = "proxy.example.com"
    ProxyBypass = "localhost;*.example.com"
}
New-NetIntentGlobalProxyOverrides @params
```

This example sets the proxy server to `proxy.example.com` and specifies that traffic to `localhost`
and any subdomains of `example.com` should bypass the proxy.

## PARAMETERS

### -AutoConfigUrl

Specifies the URL of the automatic configuration script.

```yaml
Type: String
Parameter Sets: AutoDetect
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutoDetect

Configures the system to automatically detect proxy settings.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyBypass

Specifies a list of addresses that should bypass the proxy server.

```yaml
Type: String
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyServer

Specifies the address of the proxy server.

```yaml
Type: String
Parameter Sets: Default
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[New-NetIntentAdapterPropertyOverrides](New-NetIntentAdapterPropertyOverrides.md)

[New-NetIntentAdapterRssOverrides](New-NetIntentAdapterRssOverrides.md)

[New-NetIntentGlobalClusterOverrides](New-NetIntentGlobalClusterOverrides.md)

[New-NetIntentQoSPolicyOverrides](New-NetIntentQoSPolicyOverrides.md)

[New-NetIntentSiteOverrides](New-NetIntentSiteOverrides.md)

[New-NetIntentStorageOverrides](New-NetIntentStorageOverrides.md)

[New-NetIntentSwitchConfigurationOverrides](New-NetIntentSwitchConfigurationOverrides.md)
