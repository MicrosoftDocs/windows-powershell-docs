---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: ADFS
ms.assetid: FC16D972-7D9C-48E4-A5C0-B68259042385
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Export-AdfsAuthenticationProviderConfigurationData
ms.reviewer:
---

# Export-AdfsAuthenticationProviderConfigurationData

## SYNOPSIS
Returns a file containing the tenant ID for which the AD FS farm is configured for Azure MFA, as well as the well-known client ID for Azure MFA.

## SYNTAX

```
Export-AdfsAuthenticationProviderConfigurationData -Name <String> -FilePath <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Export-AdfsAuthenticationProviderConfigurationData** cmdlet returns a file containing the tenant ID for which the Active Directory Federation Services (AD FS) farm is configured for Azure MFA, as well as the well-known client ID for Azure MFA.

Before you use this cmdlet, verify that the external authentication provider supports a custom configuration.

## EXAMPLES

### Example 1: Export configuration data
```
PS C:\> Export-AdfsAuthenticationProviderConfigurationData -Name "ContosoExternalAuthProvider" -FilePath "C:\share\test.txt"
```

This command exports configuration data for the authentication provider named ContosoExternalAuthProvider to the file C:\share\test.txt.

### Example 2: Determine which certificate Azure MFA is using
```
PS C:\> New-AdfsAzureMfaTenantCertificate -TenantID <your tenant ID> - FilePath amfacert.cer
```

This command determines which certificate Azure MFA is using, after AD FS is configured for Azure MFA.

## PARAMETERS

### -FilePath
Specifies the path and filename of the text file to which the configuration will be output.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the authentication provider to export, for example, AzureMfaAuthentication.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Import-AdfsAuthenticationProviderConfigurationData](./Import-AdfsAuthenticationProviderConfigurationData.md)

