---
external help file: Microsoft.HCS.Management.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-HcsWebProxy
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
ms.assetid: CEC8E385-7D00-4BCD-A504-4FE804F22CC7
---

# Get-HcsWebProxy

## SYNOPSIS
Gets the web proxy configuration.

## SYNTAX

```
Get-HcsWebProxy [<CommonParameters>]
```

## DESCRIPTION
The **Get-HcsWebProxy** cmdlet gets the web proxy configuration.
The cmdlet does not get the password.

## EXAMPLES

### Example 1: Get web proxy configuration
```
PS C:\> Get-HcsWebProxy
ConnectionURI                                Authentication Username                                          IsEnabled
-------------                                -------------- --------                                          ---------
None                                                       False
```

This command gets web proxy configuration for your device.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HCS.Management.Platform.Support.WebProxyInfo
The WebProxyInfo object has the following properties:

- String ConnectionURI 
- public WebProxyAuthType Authentication 
- String Username 
- IsEnabled

## NOTES

## RELATED LINKS

[Disable-HcsWebProxy](./Disable-HcsWebProxy.md)

[Enable-HcsWebProxy](./Enable-HcsWebProxy.md)

[Set-HcsWebProxy](./Set-HcsWebProxy.md)

