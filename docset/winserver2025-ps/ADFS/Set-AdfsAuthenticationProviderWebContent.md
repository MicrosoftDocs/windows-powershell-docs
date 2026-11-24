---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfsauthenticationproviderwebcontent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsAuthenticationProviderWebContent
---

# Set-AdfsAuthenticationProviderWebContent

## SYNOPSIS
Modifies a display name and description.

## SYNTAX

### IdentifierName (Default)
```
Set-AdfsAuthenticationProviderWebContent [-DisplayName <String>] [-Description <String>]
 [-UserNotProvisionedErrorMessage <String>] [-PassThru] [[-Locale] <CultureInfo>] -Name <String> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### IdentifierObject
```
Set-AdfsAuthenticationProviderWebContent [-DisplayName <String>] [-Description <String>]
 [-UserNotProvisionedErrorMessage <String>] [-PassThru] [-TargetWebContent] <AdfsAuthProviderWebContent>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsAuthenticationProviderWebContent** cmdlet modifies a display name and description.
Use this cmdlet to customize the name of the authentication provider to a user friendly and intuitive name.
You can choose to specify a locale, or use an empty string for the *Locale* parameter to specify an invariant locale.

## EXAMPLES

### Example 1: Modify the authentication provider web content
```
PS C:\> Set-AdfsAuthenticationProviderWebContent -Name MultiFactorAuthentication -DisplayName "User Friendly Name for Multifactor Authentication" -Description "Description of your choice"
```

This command modifies the display name and description for the authentication provider that the user sees in the Active Directory Federation Services (AD FS) logon pages.

## PARAMETERS

### -Description
Specifies a description.
The cmdlet modifies the provider web content with the description that you specify.

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

### -DisplayName
Specifies a display name.
The cmdlet modifies the provider web content with the display name that you specify.

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

### -Locale
Specifies a locale.
The cmdlet modifies the provider web content associated with the locale that you specify.

```yaml
Type: CultureInfo
Parameter Sets: IdentifierName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the authentication provider whose web content is being modified.
To find a list of available authentication providers, run the command `Get-AdfsAuthenticationProvider`.
Each returned provider has a **Name** property, and that value can be used with this parameter.

```yaml
Type: String
Parameter Sets: IdentifierName
Aliases:

Required: True
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

### -TargetWebContent
Specifies an **AdfsAuthenticationProviderWebContent** object that is used by the pipeline.

```yaml
Type: AdfsAuthProviderWebContent
Parameter Sets: IdentifierObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -UserNotProvisionedErrorMessage
Specifies an error message for a user not provisioned result.

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

## NOTES

## RELATED LINKS

[Get-AdfsAuthenticationProviderWebContent](./Get-AdfsAuthenticationProviderWebContent.md)

[Remove-AdfsAuthenticationProviderWebContent](./Remove-AdfsAuthenticationProviderWebContent.md)

