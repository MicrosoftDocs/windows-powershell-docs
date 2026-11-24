---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.PKIClient.Cmdlets.dll-Help.xml
Module Name: pki
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/pki/get-certificateautoenrollmentpolicy?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CertificateAutoEnrollmentPolicy
---

# Get-CertificateAutoEnrollmentPolicy

## SYNOPSIS
Retrieves certificate auto-enrollment policy settings.

## SYNTAX

```
Get-CertificateAutoEnrollmentPolicy -Scope <AutoEnrollmentPolicyScope> -Context <Context>
 [<CommonParameters>]
```

## DESCRIPTION

The `Get-CertificateAutoEnrollmentPolicy` cmdlet gets certificate auto-enrollment policy settings
for the user or computer. This cmdlet can return the settings configured in local policy or that are
being applied from either local or domain policy.

Delegation may be required when using this cmdlet with Windows PowerShell remoting and changing user
configuration.

## EXAMPLES

### EXAMPLE 1

```powershell
Get-CertificateAutoEnrollmentPolicy -Scope Local -Context User
```

```Output
PolicyState                : Enabled 
EnableMyStoreManagement    : True 
EnableTemplateCheck        : True 
ExpirationPercentage       : 10 
StoreName                  : {MY} 
EnableBalloonNotifications : False
```

This example gets the locally configured certificate auto-enrollment user policy. In this example,
the renew expired certificates, update pending certificates, remove revoked certificates, and update
certificates that use certificates templates options are enabled. Also, the expiration notifications
option is enabled and set to 10 percent of the certificate lifetime which are stored in the MY
store. Finally, balloon notifications are disabled.

## PARAMETERS

### -Scope

Specifies the scope of the enrollment policy to return. If `Local` scope is specified, then the
locally configured policy is returned. If `Applied` scope is specified, then the currently applied
policy which can be either the local policy or a domain policy, is returned.

```yaml
Type: Microsoft.CertificateServices.Commands.AutoEnrollmentPolicyScope
Parameter Sets: (All)
Aliases: 
Accepted values: Applied, Local

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Context

Specifies the context of the enrollment policy to return.

```yaml
Type: Microsoft.CertificateServices.Commands.Context
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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.CertificateServices.Commands.AutoEnrollmentPolicy

The **AutoEnrollmentPolicy** object combines certificate auto-enrollment policy settings and exposes
them as properties.

## OUTPUTS

### Microsoft.CertificateServices.Commands.AutoEnrollmentPolicy

The **AutoEnrollmentPolicy** object combines certificate auto-enrollment policy settings and exposes
them as properties. Each property can be modified and piped into the
`Set-CertificateAutoEnrollmentPolicy` cmdlet to be applied.

## NOTES

## RELATED LINKS

[Set-CertificateAutoEnrollmentPolicy](./Set-CertificateAutoEnrollmentPolicy.md)
