---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 09/19/2016
online version: https://learn.microsoft.com/powershell/module/adfs/add-adfsclient?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-AdfsClient
---

# Add-AdfsClient

## SYNOPSIS
Registers an OAuth 2.0 client with AD FS.

## SYNTAX

```
Add-AdfsClient [-ClientId] <String> [-Name] <String> [[-RedirectUri] <String[]>] [-Description <String>]
 [-ClientType <ClientType>] [-ADUserPrincipalName <String>] [-JWTSigningCertificate <X509Certificate2[]>]
 [-JWTSigningCertificateRevocationCheck <RevocationSetting>] [-JWKSUri <Uri>] [-JWKSFile <String>]
 [-LogoutUri <String>] [-GenerateClientSecret] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AdfsClient** cmdlet registers an OAuth client with Active Directory Federation Services (AD FS).
In order to allow access from OAuth clients to resources secured by AD FS, you need to register the OAuth client with AD FS by using this cmdlet.

When you register an OAuth 2.0 client with AD FS, you must specify a client identifier and a redirection URI, as well as a friendly name and description, for the OAuth client.
When an OAuth client requests access to a resource using the OAuth 2.0 protocol, the client must specify a client identifier and redirection URI to AD FS, in accordance with  [RFC 6749](https://tools.ietf.org/html/rfc6749).
AD FS will not allow access to a resource to clients that specify a client identifier or redirection URI that are not registered with AD FS.

## EXAMPLES

### Example 1: Add a client
```
PS C:\> Add-AdfsClient -Name "Payroll Application" -ClientId "ab762716-544d-4aeb-a526-687b73838a33" -RedirectUri "ms-app://s-1-15-2-2205112887-4282980309-3272664163-2407253042-283898840-27493891-3661245662/" -Description "OAuth 2.0 client for our Payroll application"
```

This command registers an OAuth 2.0 client with AD FS by using a client identifier, redirection URI, name, and description.

### Example 2: Add a client with multiple redirection URIs
```
PS C:\> Add-AdfsClient -Name "Payroll Application" -ClientId "ab762716-544d-4aeb-a526-687b73838a33" -RedirectUri @("ms-app://s-1-15-2-2205112887-4282980309-3272664163-2407253042-283898840-27493891-3661245662/", "https://Contosopayrollapplication/oauthclient/") -Description "OAuth 2.0 client for our Payroll application"
```

This command registers an OAuth 2.0 client with a client identifier, two redirection URIs, a name and description with AD FS.
The command uses two different redirections URIs to denote multiple forms of the application that may use different redirection URIs,

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

### -ClientId
Specifies the cliend ID.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClientType
Specifies the client type.
The acceptable values for this parameter are:

- Public
- Confidential

```yaml
Type: ClientType
Parameter Sets: (All)
Aliases:
Accepted values: Public, Confidential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description.

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

### -GenerateClientSecret
Indicates whether to generate a client secret.

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

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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
If the client ID and redirection URI correspond to a pre-registered OAuth 2.0 client and the resource owner authorized access by providing their credentials, AD FS will deliver the authorization code or access token by redirecting the client's user-agent back to this redirection URI.

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
Position: 2
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

### System.String

String objects are received by the *ClientId*, *Description*, *Name*, and *RedirectUri* parameters.

## OUTPUTS

### Microsoft.IdentityServer.Management.Resources.AdfsClient

Returns the new AdfsClient object when the *PassThru* parameter is specified. By default, this cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Disable-AdfsClient](./Disable-AdfsClient.md)

[Enable-AdfsClient](./Enable-AdfsClient.md)

[Get-AdfsClient](./Get-AdfsClient.md)

[Remove-AdfsClient](./Remove-AdfsClient.md)

[Set-AdfsClient](./Set-AdfsClient.md)

