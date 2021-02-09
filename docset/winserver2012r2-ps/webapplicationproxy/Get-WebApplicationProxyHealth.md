---
external help file: Microsoft.IdentityServer.ApplicationProxy.Management.PowerShell.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WebApplicationProxyHealth
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 98669250-60D7-4503-8AD9-B1E998C3695D
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WebApplicationProxyHealth

## SYNOPSIS
Gets the health status of the Web Application Proxy server.

## SYNTAX

```
Get-WebApplicationProxyHealth [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebApplicationProxyHealth** cmdlet gets the health status of the Web Application Proxy server and the health of the Web Application Proxy services on the Web Application Proxy server.

## EXAMPLES

### Example 1: Get the health of the Web Application Proxy server
```
PS C:\> Get-WebApplicationProxyHealth


Component          : AD FS Proxy
RemoteAccessServer : TSQAProxy01
HealthState        : OK
Heuristics         : {Id: 0, ErrorDesc: , ErrorCause: , ErrorResoln: , OperationStatus: , Status: OK}
TimeStamp          : 5/9/2013 6:03:03 PM


Component          : Web Application Proxy Core
RemoteAccessServer : TSQAProxy01
HealthState        : OK
Heuristics         : {Id: 0, ErrorDesc: , ErrorCause: , ErrorResoln: , OperationStatus: , Status: OK}
TimeStamp          : 5/9/2013 6:03:03 PM
```

This command gets the health status of the Web Application Proxy server.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.IdentityServer.ApplicationProxy.Management.PowerShell.Health.WebAppProxyHealthStatus
The return value is 1 if healthy, and any other value for non-healthy.

## NOTES

## RELATED LINKS

[Get-WebApplicationProxyApplication](./Get-WebApplicationProxyApplication.md)

[Get-WebApplicationProxyConfiguration](./Get-WebApplicationProxyConfiguration.md)

