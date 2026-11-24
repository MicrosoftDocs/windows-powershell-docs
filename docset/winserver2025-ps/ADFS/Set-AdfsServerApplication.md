---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 09/19/2017
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfsserverapplication?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsServerApplication
---

# Set-AdfsServerApplication

## SYNOPSIS
Modifies configuration settings for a server application role of an application in AD FS.

## SYNTAX

### Identifier (Default)
```
Set-AdfsServerApplication [-TargetIdentifier] <String> [-Identifier <String>] [-Name <String>]
 [-RedirectUri <String[]>] [-Description <String>] [-ADUserPrincipalName <String>]
 [-JWTSigningCertificate <X509Certificate2[]>] [-JWTSigningCertificateRevocationCheck <RevocationSetting>]
 [-ChangeClientSecret] [-ResetClientSecret] [-JWKSUri <Uri>] [-ReloadJWTSigningKeys] [-JWKSFile <String>]
 [-LogoutUri <String>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Name
```
Set-AdfsServerApplication [-TargetName] <String> [-Identifier <String>] [-Name <String>]
 [-RedirectUri <String[]>] [-Description <String>] [-ADUserPrincipalName <String>]
 [-JWTSigningCertificate <X509Certificate2[]>] [-JWTSigningCertificateRevocationCheck <RevocationSetting>]
 [-ChangeClientSecret] [-ResetClientSecret] [-JWKSUri <Uri>] [-ReloadJWTSigningKeys] [-JWKSFile <String>]
 [-LogoutUri <String>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ApplicationObject
```
Set-AdfsServerApplication [-TargetApplication] <ServerApplication> [-Identifier <String>] [-Name <String>]
 [-RedirectUri <String[]>] [-Description <String>] [-ADUserPrincipalName <String>]
 [-JWTSigningCertificate <X509Certificate2[]>] [-JWTSigningCertificateRevocationCheck <RevocationSetting>]
 [-ChangeClientSecret] [-ResetClientSecret] [-JWKSUri <Uri>] [-ReloadJWTSigningKeys] [-JWKSFile <String>]
 [-LogoutUri <String>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsServerApplication** cmdlet modifies configuration settings for a server application role of an application in Active Directory Federation Services (AD FS).

## EXAMPLES

## PARAMETERS

### -ADUserPrincipalName
Specifies the Active Directory account that corresponds to the confidential client that is registered.
The only client authentication method available for use with Active Directory accounts is Windows Integrated Authentication (WIA).

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
Indicates that this cmdlet changes the client secret value.

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

### -Identifier
Specifies an ID.

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

### -JWKSFile
Specifies a file that contains a JSON Web Token (JWT).

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
Specifies the URI of a JWT.

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
Specifies an array of signing certificates for JWT.
This public certificate is used to validate signatures for JWTs issued by this client for authenticating itself against AD FS by using the private key JWT client authentication method.

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
Specifies revocation checks to perform to validate signatures for JWTs sent by confidential clients.
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
Specifies an array of redirection URIs for the OAuth 2.0 client to register with AD FS.
The redirection URI is specified by the OAuth 2.0 client when it requests authorization to access a resource in ADFS.

The redirection URI specified by the client must already be registered with AD FS.
It must correspond to the client identifier for that OAuth 2.0 client.
If the client ID and redirection URI correspond to a pre-registered OAuth 2.0 client and the resource owner authorized access by providing their credentials, ADFS delivers the authorization code or access token by redirecting the client's user-agent back to this redirection URI.

The value of this parameter must match exactly the redirection URI that is specified by the OAuth 2.0 client when requesting authorization.
This includes trailing slashes '/', if they are required.
We recommended the use of more secure schemes such as https in a redirection URI.

For Windows Store applications that authenticate by using the Windows Web Authentication Broker, use the `ms-app://` scheme for a redirection URI.
If you are developing a Windows Store application, obtain the redirection URI for your application by using the following code fragment:

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
Indicates that this cmdlet reloads JWT signing keys.

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
Indicates that this cmdlet resets the client secret value.

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

### -TargetApplication
Specifies the server application.

```yaml
Type: ServerApplication
Parameter Sets: ApplicationObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetIdentifier
Specifies the ID of the server application.

```yaml
Type: String
Parameter Sets: Identifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetName
Specifies the name of the server application.

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AdfsServerApplication](./Add-AdfsServerApplication.md)

[Get-AdfsServerApplication](./Get-AdfsServerApplication.md)

[Remove-AdfsServerApplication](./Remove-AdfsServerApplication.md)

