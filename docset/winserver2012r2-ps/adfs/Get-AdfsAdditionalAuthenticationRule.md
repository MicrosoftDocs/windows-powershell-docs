---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
online version: 
schema: 2.0.0
title: Get-AdfsAdditionalAuthenticationRule
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: C48E0027-FDB7-4E1F-AF0A-76057FF592E3
---

# Get-AdfsAdditionalAuthenticationRule

## SYNOPSIS
Retrieves the global rules that trigger additional authentication providers to be invoked.

## SYNTAX

```
Get-AdfsAdditionalAuthenticationRule [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsAdditionalAuthenticationRule** cmdlet retrieves the global rules that govern all applications that trigger additional authentication providers to be invoked.
When the claim engine evaluates the additional authentication rules and determines that multiple factor authentication is required, the user is prompted to perform additional authentication.
Use this rule only when all your applications are capable of performing web based credential collection through Active Directory Federation Services (AD FS).
Applications that use protocols like WS-Trust will fail to obtain a security token if the trigger is true as a result of evaluation of the rules.

## EXAMPLES

### Example 1: Retrieve the global additional authentication rules
```
PS C:\> Get-AdfsAdditionalAuthenticationRule


c:[Type == "http://schemas.microsoft.com/2012/01/devicecontext/claims/isregistereduser", Value == "false"]
=> issue(Type = "http://schemas.microsoft.com/ws/2008/06/identity/claims/authenticationmethod", Value = "http://schemas.microsoft.com/claims/multipleauthn");

c:[Type == "http://schemas.microsoft.com/ws/2012/01/insidecorporatenetwork", Value == "false"]
=> issue(Type = "http://schemas.microsoft.com/ws/2008/06/identity/claims/authenticationmethod", Value = "http://schemas.microsoft.com/claims/multipleauthn");
```

This command retrieves the global additional authentication rules configured for AD FS.
The output of the command shows that multiple factor authentication is required for all extranet access and all devices that are not joined to a workplace.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-AdfsAdditionalAuthenticationRule](./Set-AdfsAdditionalAuthenticationRule.md)

