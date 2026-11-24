---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.Proxy.dll-Help.xml
Module Name: WebApplicationProxy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/webapplicationproxy/get-webapplicationproxysslcertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WebApplicationProxySslCertificate
---

# Get-WebApplicationProxySslCertificate

## SYNOPSIS
Gets binding information for the SSL certificate for federation server proxy.

## SYNTAX

```
Get-WebApplicationProxySslCertificate [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebApplicationProxySslCertificate** cmdlet gets binding information for the Active Directory Federation Services (AD FS) Secure Sockets Layer (SSL) certificate for the federation server proxy component of the Web Application Proxy.

## EXAMPLES

### Example 1: Get binding information for a certificate
```
PS C:\> Get-WebApplicationProxySslCertificate
```

This command gets the binding information for the AD FS SSL certificate that is installed and configured for the federation server proxy component of the Web Application Proxy.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Set-WebApplicationProxySslCertificate](./Set-WebApplicationProxySslCertificate.md)

