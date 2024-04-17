---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/import-adfsauthenticationproviderconfigurationdata?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-AdfsAuthenticationProviderConfigurationData
---

# Import-AdfsAuthenticationProviderConfigurationData

## SYNOPSIS
Imports the custom configuration for an authentication provider.

## SYNTAX

```
Import-AdfsAuthenticationProviderConfigurationData -Name <String> -FilePath <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Import-AdfsAuthenticationProviderConfigurationData** cmdlet imports custom configuration for an authentication provider from a file.
Before you use this cmdlet, verify that the external authentication provider supports a custom configuration.

Use this cmdlet when the information specific to the authentication provider changes after you initially register the authentication provider.
In some situations, the security key to access the authentication service can change and you must update the information in the Active Directory Federation Services (AD FS) configuration store for the authentication provider to function correctly.

## EXAMPLES

### Example 1: Import authentication provider configuration data
```
PS C:\> Import-AdfsAuthenticationProviderConfigurationData -Name "ContosoExternalAuthProvider" -FilePath "C:\share\test.txt"
```

This command imports the authentication provider configuration data.
This command also overwrites existing configuration data for the specified authentication provider with the data from the file.

## PARAMETERS

### -FilePath
Specifies a file path.
The cmdlet imports the configuration data from a file that you specify.

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
Specifies the name of the authentication provider to import.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Export-AdfsAuthenticationProviderConfigurationData](./Export-AdfsAuthenticationProviderConfigurationData.md)

