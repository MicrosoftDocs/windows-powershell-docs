---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.ApplicationProxy.Management.PowerShell.dll-Help.xml
Module Name: WebApplicationProxy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/webapplicationproxy/get-webapplicationproxyhealth?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WebApplicationProxyHealth
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-WebApplicationProxyApplication](./Get-WebApplicationProxyApplication.md)

[Get-WebApplicationProxyConfiguration](./Get-WebApplicationProxyConfiguration.md)

