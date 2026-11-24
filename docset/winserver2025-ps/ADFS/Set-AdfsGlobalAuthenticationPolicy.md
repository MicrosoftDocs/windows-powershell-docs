---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfsglobalauthenticationpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsGlobalAuthenticationPolicy
---

# Set-AdfsGlobalAuthenticationPolicy

## SYNOPSIS
Modifies the AD FS global policy.

## SYNTAX

```
Set-AdfsGlobalAuthenticationPolicy [-AdditionalAuthenticationProvider <String[]>]
 [-DeviceAuthenticationEnabled <Boolean>] [-DeviceAuthenticationMethod <DeviceAuthenticationMethod>]
 [-AllowDeviceAuthAsPrimaryForDomainJoinedDevices <Boolean>]
 [-PrimaryExtranetAuthenticationProvider <String[]>] [-PrimaryIntranetAuthenticationProvider <String[]>]
 [-WindowsIntegratedFallbackEnabled <Boolean>] [-ClientAuthenticationMethods <ClientAuthenticationMethod>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsGlobalAuthenticationPolicy** cmdlet modifies the Active Directory Federation Services (AD FS) global policy.
You can also use the cmdlet to enable an external provider in the global policy.

## EXAMPLES

### Example 1: Set the primary extranet authentication policy
```
PS C:\> Set-AdfsGlobalAuthenticationPolicy -PrimaryExtranetAuthenticationProvider @('FormsAuthentication', 'CertificateAuthentication')
```

This command sets the primary extranet authentication policy to forms-based or certificate-based authentication.
In this case, the user is provided a choice when the user logs on to an application protected by AD FS from the extranet.

### Example 2: Enable an additional authentication provider
```
PS C:\> Set-AdfsGlobalAuthenticationPolicy -AdditionalAuthenticationProvider "A1ExternalAuthProvider"
```

This command enables the provider named A1ExternalAuthProvider as an additional authentication provider in the global policy.
Note that the value provided for the *AdditionalAuthenticationProvider* parameter corresponds to the value you provide for the *Name* parameter in the **Register-AdfsAuthenticationProvider** cmdlet, and to the **Name** property in the output from the **Get-AdfsAuthenticationProvider** cmdlet.

## PARAMETERS

### -AdditionalAuthenticationProvider
Specifies an array of names of external authentication providers to add to the global policy.

Specifying this parameter configures an external authentication provider, for second stage authentication, in the global policy.
This is the first step in creating an AD FS policy that invokes an external authentication provider for multifactor authentication.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowDeviceAuthAsPrimaryForDomainJoinedDevices
Allows the use of device authentication as the primary type for domain-joined devices.


```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientAuthenticationMethods
Specifies the client authentication method.

```yaml
Type: ClientAuthenticationMethod
Parameter Sets: (All)
Aliases:
Accepted values: None, ClientSecretPostAuthentication, ClientSecretBasicAuthentication, PrivateKeyJWTBearerAuthentication, WindowsIntegratedAuthentication

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceAuthenticationEnabled
Specifies whether device authentication is enabled for the global policy.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceAuthenticationMethod
Specifies the device authentication method.

```yaml
Type: DeviceAuthenticationMethod
Parameter Sets: (All)
Aliases:
Accepted values: All, ClientTLS, SignedToken, PKeyAuth

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryExtranetAuthenticationProvider
Specifies an array of names of authentication providers for the primary extranet to add to the global policy.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryIntranetAuthenticationProvider
Specifies an array of names of authentication providers for the primary intranet to add to the global policy.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WindowsIntegratedFallbackEnabled
Specifies whether fallback to Integrated Windows Authentication is enabled on the intranet.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-AdfsGlobalAuthenticationPolicy](./Get-AdfsGlobalAuthenticationPolicy.md)

[Register-AdfsAuthenticationProvider](./Register-AdfsAuthenticationProvider.md)

[Get-AdfsAuthenticationProvider](./Get-AdfsAuthenticationProvider.md)

