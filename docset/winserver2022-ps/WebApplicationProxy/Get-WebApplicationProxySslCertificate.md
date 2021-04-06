---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.Proxy.dll-Help.xml
manager: jasgro
Module Name: WebApplicationProxy
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer: 
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/webapplicationproxy/get-webapplicationproxysslcertificate?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-WebApplicationProxySslCertificate](./Set-WebApplicationProxySslCertificate.md)

