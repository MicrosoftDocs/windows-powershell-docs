---
external help file: Microsoft.HCS.Management.dll-Help.xml
online version: 
schema: 2.0.0
title: Enable-HcsWebProxy
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 932D8B1B-8863-4A5A-B4A0-CA36195E0788
---

# Enable-HcsWebProxy

## SYNOPSIS
Enables the web proxy.

## SYNTAX

```
Enable-HcsWebProxy [<CommonParameters>]
```

## DESCRIPTION
The **Enable-HcsWebProxy** cmdlet enables the web proxy.
The cmdlet applies all existing configuration settings for the proxy.

## EXAMPLES

### Example 1: Enable the web proxy
```
PS C:\> Enable-HcsWebProxy


ConnectionURI                                Authentication Username                                          IsEnabled
-------------                                -------------- --------                                          ---------
http://myproxy:8080                                   Basic enarvaez                                               True
```

This command enables the web proxy for your device.
The command reverts to previous web proxy settings.
If you have not set valid values for the web proxy for this device, the command may fail.
Use the Set-HcsWebProxy cmdlet to set up the web proxy.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HCS.Management.Platform.Support.WebProxyInfoFull
The WebProxyInfo object has the following properties: 

- String ConnectionURI
- WebProxyAuthType Authentication 
- String Username
- IsEnabled

The WebProxyAuthType enumeration has the following values:

- None = proxy_auth_mech_type.AUTH_MECHANISM_NONE 
- Basic = proxy_auth_mech_type.AUTH_MECHANISM_BASIC 
- NTLM = proxy_auth_mech_type.AUTH_MECHANISM_NTLM

## NOTES

## RELATED LINKS

[Disable-HcsWebProxy](./Disable-HcsWebProxy.md)

[Get-HcsWebProxy](./Get-HcsWebProxy.md)

[Set-HcsWebProxy](./Set-HcsWebProxy.md)

