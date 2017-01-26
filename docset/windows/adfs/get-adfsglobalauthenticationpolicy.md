---
author: brianlic-msft-msft
description: 
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-AdfsGlobalAuthenticationPolicy
ms.assetid: 5820E368-96D3-4C7C-957D-74A02466BF7C
---

# Get-AdfsGlobalAuthenticationPolicy

## SYNOPSIS
Displays the AD FS global policy.

## SYNTAX

```
Get-AdfsGlobalAuthenticationPolicy [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsGlobalAuthenticationPolicy** cmdlet displays the global authentication policy, which includes the providers currently allowed as additional providers in the **AdditionalAuthenticationProvider** property.

## EXAMPLES

### Example 1: Display the global authentication policy
```
PS C:\> Get-AdfsGlobalAuthenticationPolicy


AdditionalAuthenticationProvider      : {MultiFactorAuthentication}
DeviceAuthenticationEnabled           : True
PrimaryIntranetAuthenticationProvider : {WindowsAuthentication}
PrimaryExtranetAuthenticationProvider : {FormsAuthentication, CertificateAuthentication}
WindowsIntegratedFallbackEnabled      : True
```

This command displays the global authentication policy.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Set-AdfsGlobalAuthenticationPolicy](./Set-AdfsGlobalAuthenticationPolicy.md)

