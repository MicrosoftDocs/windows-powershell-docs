---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/disable-adfswebapplicationproxyrelyingpartytrust?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-AdfsWebApplicationProxyRelyingPartyTrust
---

# Disable-AdfsWebApplicationProxyRelyingPartyTrust

## SYNOPSIS
Disables the relying party trust for the Web Application Proxy.

## SYNTAX

```
Disable-AdfsWebApplicationProxyRelyingPartyTrust [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-AdfsWebApplicationProxyRelyingPartyTrust** cmdlet disables the relying party trust object for the Web Application Proxy.
Use this cmdlet to temporarily deny all access to web applications through the proxy.
Use the **Enable-AdfsWebApplicationProxyRelyingPartyTrust** cmdlet to resume access.

The Web Application Proxy relying party trust is useful to manage global network access from outside the corporate network.
By setting authentication and authorization policies, an administrator can restrict access to internal web applications and services that are published through the Web Application Proxy.

## EXAMPLES

### Example 1: Disable access through the proxy
```
PS C:\> Disable-AdfsWebApplicationProxyRelyingPartyTrust
```

This command disables the relying party trust for the proxy, which disables external access to web applications through the proxy.

## PARAMETERS

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AdfsWebApplicationProxyRelyingPartyTrust](./Add-AdfsWebApplicationProxyRelyingPartyTrust.md)

[Enable-AdfsWebApplicationProxyRelyingPartyTrust](./Enable-AdfsWebApplicationProxyRelyingPartyTrust.md)

[Get-AdfsWebApplicationProxyRelyingPartyTrust](./Get-AdfsWebApplicationProxyRelyingPartyTrust.md)

[Remove-AdfsWebApplicationProxyRelyingPartyTrust](./Remove-AdfsWebApplicationProxyRelyingPartyTrust.md)

[Set-AdfsWebApplicationProxyRelyingPartyTrust](./Set-AdfsWebApplicationProxyRelyingPartyTrust.md)

