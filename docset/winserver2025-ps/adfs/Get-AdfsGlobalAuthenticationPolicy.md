---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/get-adfsglobalauthenticationpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AdfsGlobalAuthenticationPolicy
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Set-AdfsGlobalAuthenticationPolicy](./Set-AdfsGlobalAuthenticationPolicy.md)

