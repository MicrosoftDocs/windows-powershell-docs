---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 09/19/2017
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfsnativeclientapplication?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsNativeClientApplication
---

# Set-AdfsNativeClientApplication

## SYNOPSIS
Modifies configuration settings for a server native client application role of an application in AD FS.

## SYNTAX

### Identifier (Default)
```
Set-AdfsNativeClientApplication [-TargetIdentifier] <String> [-Identifier <String>] [-Name <String>]
 [-RedirectUri <String[]>] [-Description <String>] [-LogoutUri <String>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Name
```
Set-AdfsNativeClientApplication [-TargetName] <String> [-Identifier <String>] [-Name <String>]
 [-RedirectUri <String[]>] [-Description <String>] [-LogoutUri <String>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ApplicationObject
```
Set-AdfsNativeClientApplication [-TargetApplication] <NativeClientApplication> [-Identifier <String>]
 [-Name <String>] [-RedirectUri <String[]>] [-Description <String>] [-LogoutUri <String>] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsNativeClientApplication** cmdlet modifies configuration settings for a native client application role of an application in Active Directory Federation Services (AD FS).

## EXAMPLES

## PARAMETERS

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

### -TargetApplication
Specifies the native client application.

```yaml
Type: NativeClientApplication
Parameter Sets: ApplicationObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetIdentifier
Specifies the ID of the native client application.

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
Specifies the name of the native client application.

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

### System.String

String objects are received by the *Description*, *Identifier*, *Name*, *RedirectUri*, *TargetIdentifier*, and *TargetName* parameters.

### Microsoft.IdentityServer.Management.Resources.NativeClientApplication

NativeClientApplication objects are received by the *TargetApplication* parameter.

## OUTPUTS

### Microsoft.IdentityServer.Management.Resources.NativeClientApplication

Returns the updated NativeClientApplication object when the *PassThru* parameter is specified. By default, this cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Add-AdfsNativeClientApplication](./Add-AdfsNativeClientApplication.md)

[Get-AdfsNativeClientApplication](./Get-AdfsNativeClientApplication.md)

[Remove-AdfsNativeClientApplication](./Remove-AdfsNativeClientApplication.md)

