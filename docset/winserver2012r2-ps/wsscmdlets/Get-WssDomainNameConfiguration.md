---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssDomainNameConfiguration
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 72C2A513-95C6-4B8A-8B6E-8C310A17DBC4
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssDomainNameConfiguration

## SYNOPSIS
Gets the domain name configuration of the Windows Server Essentials computer.

## SYNTAX

```
Get-WssDomainNameConfiguration [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssDomainNameConfiguration** cmdlet gets the domain name configuration of the Windows Server Essentials computer.
This cmdlet returns Windows Server Essentials domain configuration settings, the name of the domain provider, the certificate status, and the expiration date of the certificate.

## EXAMPLES

### Example 1: Get the domain name configuration of the Windows Server
```
PS C:\> Get-WssDomainNameConfiguration
```

This command gets the domain name configuration of Windows Server Essentials.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.RemoteAccess.Domains.DomainNameConfiguration
This cmdlet generates the currently active domain name configuration object.

## NOTES

## RELATED LINKS

[Set-WssDomainNameConfiguration](./Set-WssDomainNameConfiguration.md)

