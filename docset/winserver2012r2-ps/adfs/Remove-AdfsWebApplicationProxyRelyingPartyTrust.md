---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
online version: 
schema: 2.0.0
title: Remove-AdfsWebApplicationProxyRelyingPartyTrust
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 0AEA6318-392F-4F63-87FB-FE22F132E8B2
---

# Remove-AdfsWebApplicationProxyRelyingPartyTrust

## SYNOPSIS
Removes the relying party trust object for the Web Application Proxy.

## SYNTAX

```
Remove-AdfsWebApplicationProxyRelyingPartyTrust [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AdfsWebApplicationProxyRelyingPartyTrust** cmdlet removes the relying party trust object for Web Application Proxy.
If you remove the relying party trust, Web Application Proxy blocks all external access through the proxy.
Use this cmdlet if you plan to recreate the trust later.
To temporarily block access through the proxy, you can, instead, disable the relying party trust by using the Disable-AdfsWebApplicationProxyRelyingPartyTrust cmdlet.

The Web Application Proxy relying party trust is useful to manage global network access from outside the corporate network.
By setting authentication and authorization policies, an administrator can restrict access to internal web applications and services that are published through the Web Application Proxy.

## EXAMPLES

### Example 1: Remove the relying party trust
```
PS C:\> Remove-AdfsWebApplicationProxyRelyingPartyTrust
```

This command removes the relying party trust object for the Web Application Proxy, which denies all access to web applications through the proxy.

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

[Add-AdfsWebApplicationProxyRelyingPartyTrust](./Add-AdfsWebApplicationProxyRelyingPartyTrust.md)

[Disable-AdfsWebApplicationProxyRelyingPartyTrust](./Disable-AdfsWebApplicationProxyRelyingPartyTrust.md)

[Enable-AdfsWebApplicationProxyRelyingPartyTrust](./Enable-AdfsWebApplicationProxyRelyingPartyTrust.md)

[Get-AdfsWebApplicationProxyRelyingPartyTrust](./Get-AdfsWebApplicationProxyRelyingPartyTrust.md)

[Set-AdfsWebApplicationProxyRelyingPartyTrust](./Set-AdfsWebApplicationProxyRelyingPartyTrust.md)

