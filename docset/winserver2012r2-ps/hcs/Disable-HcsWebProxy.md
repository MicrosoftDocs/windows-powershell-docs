---
external help file: Microsoft.HCS.Management.dll-Help.xml
online version: 
schema: 2.0.0
title: Disable-HcsWebProxy
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: B12BE6DD-7A8C-4DFD-99D3-F53D87379B38
---

# Disable-HcsWebProxy

## SYNOPSIS
Disables the web proxy for the device.

## SYNTAX

```
Disable-HcsWebProxy [<CommonParameters>]
```

## DESCRIPTION
The **Disable-HcsWebProxy** cmdlet disables the web proxy for the device.
This cmdlet does not delete current configuration settings.
If you enable the proxy again, the device has the same settings.

## EXAMPLES

### Example 1: Disable the web proxy
```
PS C:\> Disable-HcsWebProxy
ConnectionURI                                Authentication Username                                          IsEnabled
-------------                                -------------- --------                                          ---------
http:\\myproxy:8080                                    NTLM ENarvaez                                              False
```

This command disables the web proxy for your device.

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

[Enable-HcsWebProxy](./Enable-HcsWebProxy.md)

[Get-HcsWebProxy](./Get-HcsWebProxy.md)

[Set-HcsWebProxy](./Set-HcsWebProxy.md)

