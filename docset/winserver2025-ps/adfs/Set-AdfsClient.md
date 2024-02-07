---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 09/19/2017
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfsclient?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsClient
---

# Set-AdfsClient

## SYNOPSIS
Modifies registration settings for an OAuth 2.0 client registered with AD FS.

## SYNTAX

### Name (Default)
```
Set-AdfsClient [-Force] [-TargetName] <String> [-ClientId <String>] [-Name <String>] [-RedirectUri <String[]>]
 [-Description <String>] [-ADUserPrincipalName <String>] [-JWTSigningCertificate <X509Certificate2[]>]
 [-JWTSigningCertificateRevocationCheck <RevocationSetting>] [-ChangeClientSecret] [-ResetClientSecret]
 [-JWKSUri <Uri>] [-ReloadJWTSigningKeys] [-JWKSFile <String>] [-LogoutUri <String>] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ClientId
```
Set-AdfsClient [-Force] [-TargetClientId] <String> [-ClientId <String>] [-Name <String>]
 [-RedirectUri <String[]>] [-Description <String>] [-ADUserPrincipalName <String>]
 [-JWTSigningCertificate <X509Certificate2[]>] [-JWTSigningCertificateRevocationCheck <RevocationSetting>]
 [-ChangeClientSecret] [-ResetClientSecret] [-JWKSUri <Uri>] [-ReloadJWTSigningKeys] [-JWKSFile <String>]
 [-LogoutUri <String>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Set-AdfsClient [-Force] [-TargetClient] <AdfsClient> [-ClientId <String>] [-Name <String>]
 [-RedirectUri <String[]>] [-Description <String>] [-ADUserPrincipalName <String>]
 [-JWTSigningCertificate <X509Certificate2[]>] [-JWTSigningCertificateRevocationCheck <RevocationSetting>]
 [-ChangeClientSecret] [-ResetClientSecret] [-JWKSUri <Uri>] [-ReloadJWTSigningKeys] [-JWKSFile <String>]
 [-LogoutUri <String>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsClient** cmdlet modifies registration settings for an OAuth 2.0 client registered with Active Directory Federation Services (AD FS).
Use this cmdlet to modify the settings, including the client identifier, redirection URI, name, or description of the OAuth 2.0 client.
You can also use this cmdlet to register additional redirection URIs for the OAuth 2.0 client.

## EXAMPLES

### Example 1: Modify the redirection URI
```
PS C:\> Set-AdfsClient -TargetName "Payroll Application" -RedirectUri "https://localhost"
```

This command changes the redirection URI for the OAuth 2.0 client currently registered with AD FS with the name Payroll Application.

### Example 2:  Rename an OAuth 2.0 client
```
PS C:\> Set-AdfsClient -TargetName "Payroll Application" -Name "Payroll Application v2"
```

This command renames the OAuth 2.0 client currently registered with AD FS with the name Payroll Application.

## PARAMETERS

### -ADUserPrincipalName
Specifies an Active Directory user principal name.

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

### -ChangeClientSecret
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

### -ClientId
Specifies a string.
The cmdlet modifies the OAuth 2.0 client registration information with the identifier that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description
Specifies a description.
The cmdlet modifies the OAuth 2.0 client registration information with the description that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### -JWKSFile
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

### -JWKSUri
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

### -JWTSigningCertificate
```yaml
Type: X509Certificate2[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JWTSigningCertificateRevocationCheck
The acceptable values for this parameter are:

- None
- CheckEndCert
- CheckEndCertCacheOnly
- CheckChain
- CheckChainCacheOnly
- CheckChainExcludeRoot
- CheckChainExcludeRootCacheOnly

```yaml
Type: RevocationSetting
Parameter Sets: (All)
Aliases:
Accepted values: None, CheckEndCert, CheckEndCertCacheOnly, CheckChain, CheckChainCacheOnly, CheckChainExcludeRoot, CheckChainExcludeRootCacheOnly

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogoutUri
Specifies the logout URI for the OAuth 2.0 client to register with the AD FS. When AD FS initiates a logout it redirects the client's user-agent to this URI by rendering this URI in an iframe. The value of this parameter must be an absolute URI, may include a query component, and must not include a fragment component. This parameter is available with the Windows Update KB4038801 installed.

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
Specifies a name.
The cmdlet modifies the OAuth 2.0 client registration information with the name that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
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

### -RedirectUri
Specifies one or more redirection URIs.
The cmdlet modifies the OAuth 2.0 client registration information with the redirection URIs that you specify.

The OAuth 2.0 client uses the redirection URI when the client requests authorization to access a resource secured by AD FS.
You may register multiple redirection URIs for a single client identifier.
The redirection URI must be a valid URI.

The redirection URI specified by the client must already be registered with  AD FS and must correspond to the client identifier for that OAuth 2.0 client, in order for the client to be authorized to access the resource.
If the client ID and redirection URI correspond to a pre-registered OAuth 2.0 client and the resource owner authorized access by providing their credentials,  AD FS will deliver the authorization code or access token by redirecting the client's user-agent back to this redirection URI.

Ensure that the value of the RedirectUri parameter matches exactly the redirection URI that will be specified by the OAuth 2.0 client when requesting authorization, including trailing slashes (/), if required.
Use more secure schemes, such as https, when you specify a redirection URI.

For Windows Store applications that authenticate using the Windows Web Authentication Broker, use the 'ms-app://' scheme when registering a redirect URI.
For example, ms-app://s-1-15-2-1101140336-4090662585-1905587327-262951538-2732256205-1306401843-4235927180/ is a redirect URI for a Windows Store application.
If you are developing a Windows Store application, you can obtain the redirect URI for your application using the following code fragment:

`Uri redirectURI = Windows.Security.Authentication.Web.WebAuthenticationBroker.GetCurrentApplicationCallbackUri();`

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReloadJWTSigningKeys
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

### -ResetClientSecret
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

### -TargetClient
Specifies the registered OAuth 2.0 client to modify.

```yaml
Type: AdfsClient
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetClientId
Specifies the client identifier for the registered OAuth 2.0 client to modify.

```yaml
Type: String
Parameter Sets: ClientId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetName
Specifies the name of the registered OAuth 2.0 client to modify.

```yaml
Type: String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.IdentityServer.Management.Resources.AdfsClient

AdfsClient objects are received by the *TargetClient* parameter.

### System.String

String objects are received by the *ClientId*, *Description*, *Name*, *RedirectUri*, *TargetClientId*, and *TargetName* parameters.

## OUTPUTS

### Microsoft.IdentityServer.Management.Resources.AdfsClient

Returns the updated AdfsClient object when the *PassThru* parameter is specified. By default, this cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Add-AdfsClient](./Add-AdfsClient.md)

[Disable-AdfsClient](./Disable-AdfsClient.md)

[Enable-AdfsClient](./Enable-AdfsClient.md)

[Get-AdfsClient](./Get-AdfsClient.md)

[Remove-AdfsClient](./Remove-AdfsClient.md)

