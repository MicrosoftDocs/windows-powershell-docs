---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
online version: 
schema: 2.0.0
title: Remove-AdfsAuthenticationProviderWebContent
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 4BC225AA-0C54-48D9-8A23-CABAC266AE0A
---

# Remove-AdfsAuthenticationProviderWebContent

## SYNOPSIS
Removes web content customization of the authentication provider in the user sign-in web pages from AD FS.

## SYNTAX

### IdentifierName (Default)
```
Remove-AdfsAuthenticationProviderWebContent [[-Locale] <CultureInfo>] -Name <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### IdentifierObject
```
Remove-AdfsAuthenticationProviderWebContent [-TargetWebContent] <AdfsAuthProviderWebContent> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AdfsAuthenticationProviderWebContent** cmdlet removes web content customization of the authentication provider in the user sign-in web pages from the Active Directory Federation Services (AD FS) service.

## EXAMPLES

### Example 1: Remove authentication provider web content
```
PS C:\> Remove-AdfsAuthenticationProviderWebContent -Name "ContosoAuthenticationProvider"
```

This command removes the provider web content for the authentication provider named ContosoAuthenticationProvider.

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

### -Locale
Specifies a locale.
The cmdlet removes the provider web content associated with the locale that you specify.

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
Specifies a name.
The cmdlet gets the provider web content associated with the name that you specify.

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

## NOTES

## RELATED LINKS

[Get-AdfsAuthenticationProviderWebContent](./Get-AdfsAuthenticationProviderWebContent.md)

[Set-AdfsAuthenticationProviderWebContent](./Set-AdfsAuthenticationProviderWebContent.md)

