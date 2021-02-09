---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
online version: 
schema: 2.0.0
title: Get-AdfsGlobalAuthenticationPolicy
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
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

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Set-AdfsGlobalAuthenticationPolicy](./Set-AdfsGlobalAuthenticationPolicy.md)

