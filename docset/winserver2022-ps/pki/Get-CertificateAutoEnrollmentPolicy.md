---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.PKIClient.Cmdlets.dll-Help.xml
manager: jasgro
Module Name: pki
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer: 
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/pki/get-certificateautoenrollmentpolicy?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CertificateAutoEnrollmentPolicy
---

# Get-CertificateAutoEnrollmentPolicy

## SYNOPSIS
Retrieves certificate auto-enrollment policy settings.

## SYNTAX

```
Get-CertificateAutoEnrollmentPolicy -Scope <AutoEnrollmentPolicyScope> -context <Context> [<CommonParameters>]
```

## DESCRIPTION
The **Get-CertificateAutoEnrollmentPolicy** cmdlet gets certificate auto-enrollment policy settings for the user or computer.
This cmdlet can return the settings configured in local policy or that are being applied from either local or domain policy.

Delegation may be required when using this cmdlet with Windows PowerShell® remoting and changing user configuration.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-CertificateAutoEnrollmentPolicy -Scope Local -Context User
PolicyState                : Enabled 
EnableMyStoreManagement    : True 
EnableTemplateCheck        : True 
ExpirationPercentage       : 10 
StoreName                  : {MY} 
EnableBalloonNotifications : False
```

This example gets the locally configured certificate auto-enrollment user policy.
In this example, the Renew expired certificates, update pending certificates, and remove revoked certificates and Update certificates that use certificates templates options are enabled.
Also, the Expiration notifications option is enabled and set to 10 percent of the certificate lifetime which are stored in the MY store.
Finally, Balloon notifications are disabled.

## PARAMETERS

### -Scope
Specifies the scope of the enrollment policy to return.
If Local scope is specified, then the locally configured policy is returned.
If Applied scope is specified, then the currently applied policy which can be either the local policy or a domain policy, is returned.

```yaml
Type: AutoEnrollmentPolicyScope
Parameter Sets: (All)
Aliases: 
Accepted values: Applied, Local

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -context
Specifies the context of the enrollment policy to return.

```yaml
Type: Context
Parameter Sets: (All)
Aliases: 
Accepted values: Machine, User

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.CertificateServices.Commands.AutoEnrollmentPolicy
The **AutoEnrollmentPolicy** object combines certificate auto-enrollment policy settings and exposes them as properties.

## OUTPUTS

### Microsoft.CertificateServices.Commands.AutoEnrollmentPolicy
The **AutoEnrollmentPolicy** object combines certificate auto-enrollment policy settings and exposes them as properties.
Each property can be modified and piped into the Set-CertificateAutoEnrollmentPolicy cmdlet to be applied.

## NOTES

## RELATED LINKS

[Set-CertificateAutoEnrollmentPolicy](./Set-CertificateAutoEnrollmentPolicy.md)

