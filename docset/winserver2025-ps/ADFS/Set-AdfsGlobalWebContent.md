---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfsglobalwebcontent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsGlobalWebContent
---

# Set-AdfsGlobalWebContent

## SYNOPSIS
Sets properties for global web content objects.

## SYNTAX

### IdentifierName (Default)
```
Set-AdfsGlobalWebContent [-CompanyName <String>] [-HelpDeskLink <Uri>] [-HelpDeskLinkText <String>]
 [-HomeLink <Uri>] [-HomeLinkText <String>] [-HomeRealmDiscoveryOtherOrganizationDescriptionText <String>]
 [-HomeRealmDiscoveryPageDescriptionText <String>] [-OrganizationalNameDescriptionText <String>]
 [-PrivacyLink <Uri>] [-PrivacyLinkText <String>] [-CertificatePageDescriptionText <String>]
 [-SignInPageDescriptionText <String>] [-SignOutPageDescriptionText <String>]
 [-ErrorPageDescriptionText <String>] [-ErrorPageGenericErrorMessage <String>]
 [-ErrorPageAuthorizationErrorMessage <String>] [-ErrorPageDeviceAuthenticationErrorMessage <String>]
 [-ErrorPageSupportEmail <String>] [-UpdatePasswordPageDescriptionText <String>]
 [-SignInPageAdditionalAuthenticationDescriptionText <String>] [-PassThru] [[-Locale] <CultureInfo>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### IdentifierObject
```
Set-AdfsGlobalWebContent [-CompanyName <String>] [-HelpDeskLink <Uri>] [-HelpDeskLinkText <String>]
 [-HomeLink <Uri>] [-HomeLinkText <String>] [-HomeRealmDiscoveryOtherOrganizationDescriptionText <String>]
 [-HomeRealmDiscoveryPageDescriptionText <String>] [-OrganizationalNameDescriptionText <String>]
 [-PrivacyLink <Uri>] [-PrivacyLinkText <String>] [-CertificatePageDescriptionText <String>]
 [-SignInPageDescriptionText <String>] [-SignOutPageDescriptionText <String>]
 [-ErrorPageDescriptionText <String>] [-ErrorPageGenericErrorMessage <String>]
 [-ErrorPageAuthorizationErrorMessage <String>] [-ErrorPageDeviceAuthenticationErrorMessage <String>]
 [-ErrorPageSupportEmail <String>] [-UpdatePasswordPageDescriptionText <String>]
 [-SignInPageAdditionalAuthenticationDescriptionText <String>] [-PassThru]
 [-TargetWebContent] <AdfsGlobalWebContent> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsGlobalWebContent** cmdlet sets properties for a global web content object.
Specify a global web object by using a locale, or use the **Get-AdfsGlobalWebContent** cmdlet to obtain a web object.

## EXAMPLES

### Example 1: Set the company name for the global web content
```
PS C:\> Set-AdfsGlobalWebContent -Locale "" -CompanyName "Contoso"
```

This command sets the company name of the global web content for the invariant locale.
If there is no logo, the sign-in page displays the company name Contoso.

### Example 2: Set the text and links for the sign-in pages
```
PS C:\> Set-AdfsWebContent -Locale "en-us" -CompanyName "Contoso" -HelpDeskLink "https://helpdesklink" -HelpDeskLinkText "Help desk" -HomeLink "https://homelink" -HomeLinkText "Home" -PrivacyLink "https://privacylink" -PrivacyLinkText "Privacy statement" -SignInPageDescriptionText "Sign in here" -SignOutPageDescriptionText "Sign out here" -ErrorPageGenericErrorMessage "An error occurred." -ErrorPageSupportEmail "support@contoso.com" -UpdatePasswordPageDescriptionText "Update password here"
```

This command specifies the text to display in the sign-in pages for AD FS for the en-us locale.

### Example 3: Set the text and links for the certificate page
```
PS C:\> Set-AdfsGlobalWebContent -Locale "en-us" -CompanyName "Contoso" -HomeLink "https://homelink" -HomeLinkText "Home" -PrivacyLink "https://privaylink" -PrivacyLinkText "Privacy statement" -SignInPageDescriptionText "<p>Sign-in to Contoso requires device registration. Click <A href='https://fs1.contoso.com/deviceregistration/'>here</A> for more information.</p>" -SignOutPageDescriptionText "Sign out here" -ErrorPageGenericErrorMessage "An error occurred." -ErrorPageSupportEmail "support@contoso.com" -UpdatePasswordPageDescriptionText "Update password here" -CertificatePageDescriptionText "Sign in with your Smartcard"
```

This command specifies the text and links to display when an application prompts a user prompted for a certificate.

## PARAMETERS

### -CertificatePageDescriptionText
Specifies the text on the certificate page.
Active Directory Federation Services (AD FS) displays the text that you specify when it prompts the user for a certificate.
In earlier versions of AD FS, the user sees a blank page when AD FS prompts the user for a certificate.

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
Specifies the company name.
AD FS displays the company name in the sign-in pages when you have not set a logo on the active web theme.

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
You can override this message for an application by using the **Set-AdfsRelyingPartyWebContent** cmdlet.

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
Specifies an error message to display when a user encounters any generic errors that occur for a token request.
This string can be an HTML fragment.
You can override this message for an application by using the **Set-AdfsRelyingPartyWebContent** cmdlet.

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
Device authentication errors occur when the user presents an expired user@device certificate to AD FS, a certificate is not found in AD DS, or a certificate is disabled in AD DS.
This string can be an HTML fragment.
You can override this message for an application by using the **Set-AdfsRelyingPartyWebContent** cmdlet.

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
You can override this message for an application by using the **Set-AdfsRelyingPartyWebContent** cmdlet.

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
Specifies the support email address on the error page.

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
Specifies the help desk link that is shown on the logon pages for AD FS.

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
Specifies the help desk link text that is shown on the logon pages for AD FS.

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
Specifies the Home link that is shown on the logon pages for AD FS.

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
Specifies the Home link text that is shown on the logon pages for AD FS.

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
Specifies the text for the home realm discovery description for other organization.

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
Specifies the text for the home realm discovery page description.

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
The cmdlet sets global web content for the locale that you specify.

```yaml
Type: CultureInfo
Parameter Sets: IdentifierName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -OrganizationalNameDescriptionText
Specifies text for the organizational name description.

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
Specifies the Privacy policy link that is shown on the logon pages for AD FS.

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
Specifies the Privacy policy link text that is shown on the logon pages for AD FS.

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
Specifies the description to display when an application prompts a user for additional authentication.
The sign-in page can also display a description that is provided by the additional authentication provider.

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
Specifies the description to display when a user signs in to applications by using AD FS.
When you use Integrated Windows Authentication in the intranet, users do not see this page.

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

### -SignOutPageDescriptionText
Specifies the description to display when a user signs out of applications.

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

### -TargetWebContent
Specifies an **AdfsGlobalWebContent** object.
The cmdlet modifies content for the object that you specify.
To obtain a **AdfsGlobalWebContent** object, use the **Get-AdfsGlobalWebContent** cmdlet.

```yaml
Type: AdfsGlobalWebContent
Parameter Sets: IdentifierObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -UpdatePasswordPageDescriptionText
Specifies the description to display in the update password page when users change their passwords.

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

### System.IdentityServer.Management.Resources.AdfsGlobalWebContent
This cmdlet generates a **System.IdentityServer.Management.Resources.AdfsGlobalWebContent** object that represents global web content.
The object includes the following properties:

- Locale: **System.Globalization.CultureInfo**
- CompanyName: **System.String**
- HelpDeskLink: **System.Uri**
- HelpDeskLinkText: **System.String**
- HomeLink: **System.Uri**
- HomeLinkText: **System.String**
- PrivacyLink: **System.Uri**
- PrivacyLinkText: **System.String**
- SignInPageDescriptionText: **System.String**
- SignOutPageDescriptionText: **System.String**
- ErrorPageDescriptionText: **System.String**
- ErrorPageGenericErrorMessage: **System.String**
- ErrorPageAuthorizationErrorMessage: **System.String**
- ErrorPageDeviceAuthenticationErrorMessage: **System.String**
- ErrorPageSupportEmail: **System.String**
- UpdatePasswordPageDescriptionText: **System.String**
- SignInPageAdditionalAuthenticationDescriptionText: **System.String**

## NOTES

## RELATED LINKS

[Get-AdfsGlobalWebContent](./Get-AdfsGlobalWebContent.md)

[Remove-AdfsGlobalWebContent](./Remove-AdfsGlobalWebContent.md)

[Set-AdfsRelyingPartyWebContent](./Set-AdfsRelyingPartyWebContent.md)

