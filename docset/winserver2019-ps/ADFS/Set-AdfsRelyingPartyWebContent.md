---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfsrelyingpartywebcontent?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsRelyingPartyWebContent
---

# Set-AdfsRelyingPartyWebContent

## SYNOPSIS
Sets properties for the relying party web content objects.

## SYNTAX

### IdentifierName (Default)
```
Set-AdfsRelyingPartyWebContent [-CertificatePageDescriptionText <String>] [-CompanyName <String>]
 [-ErrorPageDescriptionText <String>] [-ErrorPageGenericErrorMessage <String>]
 [-ErrorPageAuthorizationErrorMessage <String>] [-ErrorPageDeviceAuthenticationErrorMessage <String>]
 [-ErrorPageSupportEmail <String>] [-HelpDeskLink <Uri>] [-HelpDeskLinkText <String>] [-HomeLink <Uri>]
 [-HomeLinkText <String>] [-HomeRealmDiscoveryOtherOrganizationDescriptionText <String>]
 [-HomeRealmDiscoveryPageDescriptionText <String>] [-OrganizationalNameDescriptionText <String>]
 [-PrivacyLink <Uri>] [-PrivacyLinkText <String>] [-SignInPageDescriptionText <String>]
 [-SignInPageAdditionalAuthenticationDescriptionText <String>] [-PassThru] [[-Locale] <CultureInfo>]
 -TargetRelyingPartyName <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdentifierObject
```
Set-AdfsRelyingPartyWebContent [-CertificatePageDescriptionText <String>] [-CompanyName <String>]
 [-ErrorPageDescriptionText <String>] [-ErrorPageGenericErrorMessage <String>]
 [-ErrorPageAuthorizationErrorMessage <String>] [-ErrorPageDeviceAuthenticationErrorMessage <String>]
 [-ErrorPageSupportEmail <String>] [-HelpDeskLink <Uri>] [-HelpDeskLinkText <String>] [-HomeLink <Uri>]
 [-HomeLinkText <String>] [-HomeRealmDiscoveryOtherOrganizationDescriptionText <String>]
 [-HomeRealmDiscoveryPageDescriptionText <String>] [-OrganizationalNameDescriptionText <String>]
 [-PrivacyLink <Uri>] [-PrivacyLinkText <String>] [-SignInPageDescriptionText <String>]
 [-SignInPageAdditionalAuthenticationDescriptionText <String>] [-PassThru]
 [-TargetRelyingPartyWebContent] <AdfsRelyingPartyWebContent> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsRelyingPartyWebContent** cmdlet sets properties for a relying party web content object.
These properties override equivalent values set by using the **Set-AdfsGlobalWebContent** cmdlet to obtain a web content object.
Specify a relying party web content object by using a name and locale, or use the **Get-AdfsRelyingPartyWebContent** cmdlet.
If you do not specify a locale, the cmdlet uses the invariant locale.

## EXAMPLES

### Example 1: Specify a generic error message
```
PS C:\> Set-AdfsRelyingPartyWebContent -Name "RelyingParty01" -ErrorPageGenericErrorMessage "There is an error."
```

This command specifies a generic error message to display to users for the relying party named RelyingParty01.

### Example 2: Specify multiple error messages
```
PS C:\> Set-AdfsRelyingPartyWebContent -Locale en-us -Name "RelyingParty02" -ErrorPageAuthorizationErrorMessage "There is an authorization error." -ErrorPageDeviceAuthenticationErrorMessage "There is a device authentication error." -ErrorPageGenericErrorMessage "There is an error."
```

This command assigns multiple error messages to display to users for the relying party named RelyingParty01 with the specified locale.

### Example 2: Create a custom message on the Sign in page
```
PS C:\> Set-AdfsRelyingPartyWebContent -SignInPageDescription "If you have forgotten your password, visit <A href='https://passwordreset.microsoftonline.com/'>Microsoft Entra self-service password reset</A>." -TargetRelyingPartyName "Microsoft Office 365 Identity Platform"
```

The command creates a custom message on the Sign in page for the Office 365 relying party.

## PARAMETERS

### -CertificatePageDescriptionText
Specifies text to display under the text for the *CompanyName* parameter on the certificate selection page.

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

### -CompanyName
Specifies the heading text on Sign in page.

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

### -ErrorPageDescriptionText
Specifies the text under the text for the *CompanyName* parameter on the Sign in error page.

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

### -ErrorPageSupportEmail
Specifies the email address to display on the Sign in error page.

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

### -HelpDeskLink
Specifies the target of the Help Desk link at the bottom of the Sign in page.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HelpDeskLinkText
Specifies the text of the Help Desk link at the bottom of the Sign in page.

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

### -HomeLink
Specifies the target of the Home link at the bottom of the Sign in page.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HomeLinkText
Specifies the text of the Home link at the bottom of the Sign in page.

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

### -HomeRealmDiscoveryOtherOrganizationDescriptionText
Specifies a description displayed above the user name entry prompt.
If you configure a UPN suffix mapping to one or more claims provider trusts, the home realm discovery page features an option for Other organization.
If users select this option, they are prompted to enter a user name.

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

### -HomeRealmDiscoveryPageDescriptionText
Specifies text to display under the text for the *CompanyName* parameter on the home realm discovery page.

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

### -OrganizationalNameDescriptionText
Specifies the text under the text for the *CompanyName* parameter on the Sign in page.

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

### -PrivacyLink
Specifies the target of the Privacy link at the bottom of the Sign in page.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrivacyLinkText
Specifies the text of the Privacy link at the bottom of the Sign in page.

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

### -SignInPageAdditionalAuthenticationDescriptionText
Specifies the text under the text for the *CompanyName* parameter on the additional authentication choice page.

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

### -SignInPageDescriptionText
Specifies the text under the sign in options on the Sign in page.

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

### -TargetRelyingPartyName
Specifies the name of the relying party trust to modify.

```yaml
Type: String
Parameter Sets: IdentifierName
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetRelyingPartyWebContent
Specifies the name of the relying party web content to modify.

```yaml
Type: AdfsRelyingPartyWebContent
Parameter Sets: IdentifierObject
Aliases: TargetWebContent

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### System.IdentityServer.Management.Resources.AdfsRelyingPartyWebContent
This cmdlet generates a **System.IdentityServer.Management.Resources.AdfsRelyingPartyWebContent** object that represents web content of a relying party, or an array of such objects.
The object includes the following properties: 

- Locale: **System.Globalization.CultureInfo**
- Name: **System.String**
- ErrorPageGenericErrorMessage: **System.String**
- ErrorPageAuthorizationErrorMessage: **System.String**
- ErrorPageDeviceAuthenticationErrorMessage: **System.String**

## NOTES

## RELATED LINKS

[Get-AdfsRelyingPartyWebContent](./Get-AdfsRelyingPartyWebContent.md)

[Remove-AdfsRelyingPartyWebContent](./Remove-AdfsRelyingPartyWebContent.md)

