---
author: brianlic-msft
description: 
external help file: Microsoft.IdentityServer.Management.Proxy.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-WebApplicationProxySslCertificate
ms.assetid: 47E4876B-2FC2-4D2A-8C5C-66DA678B3B19
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-WebApplicationProxySslCertificate](./Set-WebApplicationProxySslCertificate.md)

