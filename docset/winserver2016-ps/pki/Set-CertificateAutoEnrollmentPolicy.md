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
online version: https://docs.microsoft.com/powershell/module/pki/set-certificateautoenrollmentpolicy?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-CertificateAutoEnrollmentPolicy
---

# Set-CertificateAutoEnrollmentPolicy

## SYNOPSIS
Sets local certificate auto-enrollment policy.

## SYNTAX

### EnableSeparately
```
Set-CertificateAutoEnrollmentPolicy [-StoreName <String[]>] -PolicyState <PolicySetting>
 [-ExpirationPercentage <Int32>] [-EnableTemplateCheck] [-EnableMyStoreManagement]
 [-EnableBalloonNotifications] -context <Context> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### EnableAll
```
Set-CertificateAutoEnrollmentPolicy [-EnableAll] -context <Context> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-CertificateAutoEnrollmentPolicy** cmdlet configures local certificate auto-enrollment policy for a user or computer.
The auto-enrollment policy can also be configured by using the Local Security Policy console.
These settings can be found in the following location. 

 -- `\Security Settings\Public Key Policies\Certificate Services Client - Auto-Enrollment`.

Delegation may be required when using this cmdlet with Windows PowerShell® remoting and changing user configuration.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-CertificateAutoEnrollmentPolicy -PolicyState Enabled -EnableMyStoreManagement -EnableTemplateCheck -Context User
```

This example enables local user certificate auto-enrollment policy with the Renew expired certificates, update pending certificates, and remove revoked certificates and Update certificates that use certificates templates options enabled.

### EXAMPLE 2
```
PS C:\>Set-CertificateAutoEnrollmentPolicy -PolicyState NotConfigured -Context Machine
```

This example sets local computer certificate auto-enrollment policy to Not Configured.

### EXAMPLE 3
```
PS C:\>Set-CertificateAutoEnrollmentPolicy -ExpirationPercentage 15 -PolicyState Enabled -EnableExpirationNotification -Context Machine -StoreName "Remote Desktop"
```

This example enables local computer certificate auto-enrollment policy with the Expiration notifications option enabled and set to 15 percent of the certificate lifetime.
This cmdlet also configures the Remote Desktop certificate store as an additional store to be monitored for certificate expiration.

### EXAMPLE 4
```
The example in detail.
PS C:\>Set-CertificateAutoEnrollmentPolicy -PolicyState Enabled -EnableMyStoreManagement -EnableTemplateCheck -EnableExpirationNotification -ExpirationPercentage 10 -Context User


The concise version of the same example.
PS C:\>Set-CertificateAutoEnrollmentPolicy -EnableAll -Context User
```

This example performs the same task in two ways.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableAll
Enables all of the auto-enrollment policy settings and sets the value for the expiration percentage to 10 percent.
If this parameter is enabled, then only the **Context** parameter is required and all other parameters are optional.

```yaml
Type: SwitchParameter
Parameter Sets: EnableAll
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableBalloonNotifications
Enables the Expiration balloon notifications option for the certificate auto-enrollment policy.

```yaml
Type: SwitchParameter
Parameter Sets: EnableSeparately
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableMyStoreManagement
Enables the Renew expired certificates, update pending certificates, and remove revoked certificates option for the certificate auto-enrollment policy.

```yaml
Type: SwitchParameter
Parameter Sets: EnableSeparately
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableTemplateCheck
Verifies that existing certificates are based on the most recent version of a certificate template and updates them if they are not.

```yaml
Type: SwitchParameter
Parameter Sets: EnableSeparately
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExpirationPercentage
Sets the percentage of the certificate lifetime at which close-to-expiration events are logged and auto-enrollment notifications start to appear.

```yaml
Type: Int32
Parameter Sets: EnableSeparately
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PolicyState
Specifies the state of the certificate auto-enrollment policy configuration.

```yaml
Type: PolicySetting
Parameter Sets: EnableSeparately
Aliases: 
Accepted values: NotConfigured, Enabled, Disabled

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StoreName
Specifies additional comma separated certificate stores to monitor for certificates that have expired or are expiring.
The MY store is always monitored.

```yaml
Type: String[]
Parameter Sets: EnableSeparately
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -context
Specifies whether to set certificate auto-enrollment policy for the user or computer context.

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
Each property can be modified and piped into this cmdlet to be applied.

## NOTES

## RELATED LINKS

[Get-CertificateAutoEnrollmentPolicy](./Get-CertificateAutoEnrollmentPolicy.md)

