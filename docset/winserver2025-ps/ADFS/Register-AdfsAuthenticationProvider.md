---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/register-adfsauthenticationprovider?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Register-AdfsAuthenticationProvider
---

# Register-AdfsAuthenticationProvider

## SYNOPSIS
Registers an external authentication provider in AD FS.

## SYNTAX

```
Register-AdfsAuthenticationProvider -TypeName <String> -Name <String> [-ConfigurationFilePath <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Register-AdfsAuthenticationProvider** cmdlet registers an external authentication provider as a provider in Active Directory Federation Services (AD FS).
Use the **Get-AdfsAuthenticationProvider** cmdlet to get a list of registered authentication providers.

## EXAMPLES

### Example 1: Register an authentication provider
```
PS C:\> $TypeName = "ExternalAuthMethod.ExternalAuthProvider, ExternalAuthProvider, Version=1.0.0.0, Culture=neutral, PublicKeyToken=365143bb27e7ac8b, processorArchitecture=MSIL"
PS C:\> Register-AdfsAuthenticationProvider -TypeName $TypeName -Name "MyExternalAuthProvider" -ConfigurationFilePath ".\configdata.txt"
```

The first command creates a variable named $TypeName that contains the configuration data for an external provider.

The second command registers the authentication provider by using the data stored in the $TypeName variable.

## PARAMETERS

### -ConfigurationFilePath
Specifies the fully qualified file path of a file that contains authentication provider configuration data.

You can also upload the file to the Active Directory Federation Services (AD FS) configuration store and make it available to the authentication provider.
Use this method if you want to provide additional information that pertains to a specific customer when you initialize the authentication provider.
Any usage of this method is specific to the vendor that supplies the authentication provider.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of an authentication provider to register in AD FS.

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

### -TypeName
Specifies the fully qualified type of the authentication provider assembly on the federation server.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-AdfsAuthenticationProvider](./Get-AdfsAuthenticationProvider.md)

[Unregister-AdfsAuthenticationProvider](./Unregister-AdfsAuthenticationProvider.md)

