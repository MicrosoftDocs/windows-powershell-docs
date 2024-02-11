---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.Proxy.dll-Help.xml
Module Name: WebApplicationProxy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/webapplicationproxy/set-webapplicationproxysslcertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WebApplicationProxySslCertificate
---

# Set-WebApplicationProxySslCertificate

## SYNOPSIS
Installs an SSL certificate for a federation server proxy.

## SYNTAX

```
Set-WebApplicationProxySslCertificate -Thumbprint <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WebApplicationProxySslCertificate** cmdlet installs and configures an Active Directory Federation Services (AD FS) Secure Sockets Layer (SSL) certificate for the federation server proxy component of the Web Application Proxy.

## EXAMPLES

### Example 1: Configure a certificate for use
```
PS C:\> Set-WebApplicationProxySslCertificate -Thumbprint "FC85DDB0FC58E63D8CB52654F22E4BE7900FE349"
```

This command installs the certificate specified by the thumbprint, and configures the certificate for use by the federation server proxy component.

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

### -Thumbprint
Specifies the thumbprint of an X.509 certificate.
This cmdlet sets the certificate that this parameter specifies as the AD FS SSL certificate that Web Application Proxy installs and configure for the federation server proxy component.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-WebApplicationProxySslCertificate](./Get-WebApplicationProxySslCertificate.md)

