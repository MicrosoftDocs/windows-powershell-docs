---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: WebApplicationProxy-help.xml
Module Name: WebApplicationProxy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/webapplicationproxy/set-webapplicationproxyconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WebApplicationProxyConfiguration
---

# Set-WebApplicationProxyConfiguration

## SYNOPSIS
Modifies the configuration settings of a Web Application Proxy server.

## SYNTAX

```
Set-WebApplicationProxyConfiguration [-ADFSUrl <Uri>] [-ADFSTokenSigningCertificatePublicKey <String>]
 [-ADFSWebApplicationProxyRelyingPartyUri <Uri>] [-RegenerateAccessCookiesEncryptionKey]
 [-ConnectedServersName <String[]>] [-OAuthAuthenticationURL <Uri>]
 [-ConfigurationChangesPollingIntervalSec <UInt32>] [-UpgradeConfigurationVersion]
 [-ADFSTokenAcceptanceDurationSec <UInt32>] [-ADFSSignOutURL <Uri>] [-UserIdleTimeoutSec <UInt32>]
 [-UserIdleTimeoutAction <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-WebApplicationProxyConfiguration** cmdlet modifies the configuration settings of a Web Application Proxy server.
The settings include the Active Directory Federation Services (AD FS) URL, the token signing certificate, and the edge server URI.

## EXAMPLES

### Example 1: Modify the proxy to check for configuration changes
```
PS C:\> Set-WebApplicationProxyConfiguration -ConfigurationChangesPollingIntervalSec 300
```

This command modifies the Web Application Proxy to query the federation server every 300 seconds for configuration changes.

## PARAMETERS

### -ADFSSignOutURL
Specifies the sign out URL for Web Application Proxy.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ADFSTokenAcceptanceDurationSec
Specifies the maximum duration in seconds until when the Web Application Proxy server accepts the edge token issued by the AD FS server.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ADFSTokenSigningCertificatePublicKey
Specifies the thumbprint of the certificate that the federation server uses to sign the edge token.
The thumbprint is the SHA-1 hash of the certificate and consists of 40 hexadecimal characters.
Specify this parameter only when the AD FS token signing certificate changes.

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

### -ADFSUrl
Specifies the URL for the federation server that is used by the Web Application Proxy.
The Web Application Proxy Configuration Wizard populates this setting, and there is no requirement that you manually change it.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ADFSWebApplicationProxyRelyingPartyUri
Specifies the URI for the Web Application Proxy server.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigurationChangesPollingIntervalSec
Specifies the time interval, in seconds, that elapses before the Web Application Proxy servers query a federation server for configuration changes.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectedServersName
Specifies an array of Web Application Proxy servers that are connected to a federation server.

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

### -OAuthAuthenticationURL
Specifies the URL of the federation server that performs Open Authorization (OAuth) authentication when end users connect to a published web application using a Windows Store app.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RegenerateAccessCookiesEncryptionKey
Specifies whether to create a new encryption key to be used by Web Application Proxy servers to encrypt proxy cookies.
All Web Application Proxy servers use the encryption key to validate the access cookie, even if the cookie was issued by another Web Application Proxy server.

You should specify this parameter whenever you want to change the encryption key that is used to encrypt the proxy cookies.

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

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpgradeConfigurationVersion
Indicates whether this cmdlet uses the upgrade configuration version setting.

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

### -UserIdleTimeoutAction
Specifies whether inactive user will be redirected to the AD FS for signout or reauthentication.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Signout, Reauthenticate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserIdleTimeoutSec
Specifies the inactivity time interval, in seconds, after which Web Application Proxy will redirect users to AD FS.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Uri

### System.String

### System.String[]

### System.UInt32

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-WebApplicationProxyConfiguration](./Get-WebApplicationProxyConfiguration.md)
