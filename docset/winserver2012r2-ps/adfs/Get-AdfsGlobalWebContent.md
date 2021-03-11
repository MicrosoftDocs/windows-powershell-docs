---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
online version: 
schema: 2.0.0
title: Get-AdfsGlobalWebContent
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: C021BA1C-42EA-4FC4-B36B-9D20A88772BF
---

# Get-AdfsGlobalWebContent

## SYNOPSIS
Gets global web content objects.

## SYNTAX

```
Get-AdfsGlobalWebContent [-Locale <CultureInfo[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsGlobalWebContent** cmdlet gets all global web content objects or the global web content object that corresponds to the locale that you specify.
If you do not specify the **Locale** parameter, the cmdlet gets global web content objects for all locales.

## EXAMPLES

### Example 1: Get global web content for all locales
```
PS C:\> Get-AdfsGlobalWebContent


Locale                                            :
CompanyName                                       :
HelpDeskLink                                      :
HelpDeskLinkText                                  :
HomeLink                                          :
HomeLinkText                                      :
PrivacyLink                                       :
PrivacyLinkText                                   :
CertificatePageDescriptionText                    :
SignInPageDescriptionText                         :
SignOutPageDescriptionText                        :
ErrorPageDescriptionText                          :
ErrorPageGenericErrorMessage                      :
ErrorPageAuthorizationErrorMessage                : You have been denied access.
ErrorPageDeviceAuthenticationErrorMessage         :
ErrorPageSupportEmail                             :
UpdatePasswordPageDescriptionText                 :
SignInPageAdditionalAuthenticationDescriptionText :
```

This command gets the global web content for all locales.

### Example 2: Get the global web content for a locale
```
PS C:\> Get-AdfsGlobalWebContent -Locale en-us
```

This command gets the global web content for the en-us locale.
If you did not specify a locale when you modified properties of the global web content by using the Set-AdfsGlobalWebContent cmdlet, the cmdlet returns no additional information.

## PARAMETERS

### -Locale
Specifies an array of locales.
The cmdlet gets the global web content associated with the locales that you specify.

```yaml
Type: CultureInfo[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.IdentityServer.Management.Resources.AdfsGlobalWebContent;Microsoft.IdentityServer.Management.Resources.AdfsGlobalWebContent[]
This cmdlet generates a **System.IdentityServer.Management.Resources.AdfsGlobalWebContent** object that represents global web content.
The object includes the following properties:

Locale: **System.Globalization.CultureInfo**
CompanyName: **System.String**
HelpDeskLink: **System.Uri**
HelpDeskLinkText: **System.String**
HomeLink: **System.Uri**
HomeLinkText: **System.String**
PrivacyLink: **System.Uri**
PrivacyLinkText: **System.String**
SignInPageDescriptionText: **System.String**
SignOutPageDescriptionText: **System.String**
ErrorPageDescriptionText: **System.String**
ErrorPageGenericErrorMessage: **System.String**
ErrorPageAuthorizationErrorMessage: **System.String**
ErrorPageDeviceAuthenticationErrorMessage: **System.String**
ErrorPageSupportEmail: **System.String**
ErrorPageSupportEmailText: **System.String**
UpdatePasswordPageDescriptionText: **System.String**
CertificatePageDescriptionText: **System.String**
SignInPageAdditionalAuthenticationDescriptionText: **System.String**

## NOTES

## RELATED LINKS

[Get-AdfsGlobalWebContent](./Get-AdfsGlobalWebContent.md)

[Set-AdfsGlobalWebContent](./Set-AdfsGlobalWebContent.md)

[Remove-AdfsGlobalWebContent](./Remove-AdfsGlobalWebContent.md)

