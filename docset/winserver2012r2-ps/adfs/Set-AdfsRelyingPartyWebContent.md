---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
online version: 
schema: 2.0.0
title: Set-AdfsRelyingPartyWebContent
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 0247F887-E1F9-47F5-A61E-64FA0B65ED08
---

# Set-AdfsRelyingPartyWebContent

## SYNOPSIS
Sets properties for the relying party web content objects.

## SYNTAX

### IdentifierName (Default)
```
Set-AdfsRelyingPartyWebContent [-ErrorPageGenericErrorMessage <String>]
 [-ErrorPageAuthorizationErrorMessage <String>] [-ErrorPageDeviceAuthenticationErrorMessage <String>]
 [-PassThru] [[-Locale] <CultureInfo>] -Name <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdentifierObject
```
Set-AdfsRelyingPartyWebContent [-ErrorPageGenericErrorMessage <String>]
 [-ErrorPageAuthorizationErrorMessage <String>] [-ErrorPageDeviceAuthenticationErrorMessage <String>]
 [-PassThru] [-TargetWebContent] <AdfsRelyingPartyWebContent> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsRelyingPartyWebContent** cmdlet sets properties for a relying party web content object.
These properties override equivalent values set by using the Set-AdfsGlobalWebContent cmdlet to obtain a web content object.
Specify a relying party web content object by using a name and locale, or use the Get-AdfsRelyingPartyWebContent cmdlet.
If you do not specify a locale, the cmdlet uses the invariant locale.

## EXAMPLES

### Example 1: Specify a generic error message
```
PS C:\> Set-AdfsRelyingPartyWebContent -Name "RelyingParty01" -ErrorPageGenericErrorMessage "There is an error."
```

This command specifies a generic error message to display to users for the relying party named RelyingParty01.

### Example 2: Specify multiple error messages
```
PS C:\> Set-AdfsRelyingPartyWebContent -Locale en-us -Name "RelyingParty02"  -ErrorPageAuthorizationErrorMessage "There is an authorization error." -ErrorPageDeviceAuthenticationErrorMessage "There is a device authentication error." -ErrorPageGenericErrorMessage "There is an error."
```

This command assigns multiple error messages to display to users for the relying party named RelyingParty01 with the specified locale.

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

### -ErrorPageAuthorizationErrorMessage
Specifies an error message to display when a user encounters any authorization errors that occur for a token request.
This string can be an HTML fragment.

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

### -ErrorPageDeviceAuthenticationErrorMessage
Specifies an error message to display for any device authentication errors that occur for a token request.
Device authentication errors occur when the user presents an expired user@device certificate to Active Directory Federation Services (AD FS), a certificate that is not found in Active Directory® Domain Services, or a certificate that is disabled in Active Directory Domain Services.
This string can be an HTML fragment.

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

### -ErrorPageGenericErrorMessage
Specifies an error message to display for any generic errors that occur for a token request.
This string can be an HTML fragment.

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
The cmdlet sets relying party web content for the locale that you specify.

```yaml
Type: CultureInfo
Parameter Sets: IdentifierName
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name.
The cmdlet modifies content for the relying party that you specify by name.

```yaml
Type: String
Parameter Sets: IdentifierName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Specifies a relying party web content object.
The cmdlet modifies content for the object that you specify.
To obtain a relying party web content object, use **Get-AdfsRelyingPartyWebContent**.

```yaml
Type: AdfsRelyingPartyWebContent
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

### System.IdentityServer.Management.Resources.AdfsRelyingPartyWebContent
This cmdlet generates a **System.IdentityServer.Management.Resources.AdfsRelyingPartyWebContent** object that represents web content of a relying party, or an array of such objects.
The object includes the following properties: 

Locale: **System.Globalization.CultureInfo**
Name: **System.String**
ErrorPageGenericErrorMessage: **System.String**
ErrorPageAuthorizationErrorMessage: **System.String**
ErrorPageDeviceAuthenticationErrorMessage: **System.String**

## NOTES

## RELATED LINKS

[Get-AdfsRelyingPartyWebContent](./Get-AdfsRelyingPartyWebContent.md)

[Remove-AdfsRelyingPartyWebContent](./Remove-AdfsRelyingPartyWebContent.md)

