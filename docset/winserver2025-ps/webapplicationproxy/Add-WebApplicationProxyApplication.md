---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: WebApplicationProxy-help.xml
Module Name: WebApplicationProxy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/webapplicationproxy/add-webapplicationproxyapplication?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WebApplicationProxyApplication
---

# Add-WebApplicationProxyApplication

## SYNOPSIS
Publishes a web application through Web Application Proxy.

## SYNTAX

```
Add-WebApplicationProxyApplication [-Name] <String> [-ExternalPreauthentication <String>]
 [-ClientCertificateAuthenticationBindingMode <String>] [-BackendServerCertificateValidation <String>]
 -ExternalUrl <String> [-ExternalCertificateThumbprint <String>] [-EnableSignOut]
 [-InactiveTransactionsTimeoutSec <UInt32>] [-ClientCertificatePreauthenticationThumbprint <String>]
 [-EnableHTTPRedirect] [-ADFSUserCertificateStore <String>] [-DisableHttpOnlyCookieProtection]
 [-PersistentAccessCookieExpirationTimeSec <UInt32>] -BackendServerUrl <String>
 [-DisableTranslateUrlInRequestHeaders] [-DisableTranslateUrlInResponseHeaders]
 [-BackendServerAuthenticationSPN <String>] [-ADFSRelyingPartyName <String>] [-UseOAuthAuthentication]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Add-WebApplicationProxyApplication** cmdlet publishes a web application through Web Application Proxy.
Use this cmdlet to specify a name for the web application, and to provide an external address and the address of the backend server.
External clients connect to the external address to access the web application hosted by the backend server.
The cmdlet checks the external address to verify that no other published web application uses it on any of the proxies in the current Active Directory Federation Services (AD FS) installation.

You can specify the relying party for use with AD FS, the service principal name (SPN) of the backend server, a certificate thumbprint for the external address, the method of preauthentication, and whether the proxy provides the URL of the federation server to users of Open Authorization (OAuth).
You can also specify whether the application proxy validates the certificate from the backend server and verifies whether the certificate that authenticates the federation server authenticates future requests.

The proxy can translate URLs in headers.
You can disable translation in either request or response headers, or both.

You can also specify a time-out value for inactive connections.

This cmdlet supports passing multiple **WebApplicationProxyApplication** objects through the pipeline.

## EXAMPLES

### Example 1: Publish a web application
```
PS C:\> Add-WebApplicationProxyApplication -Name "Contoso App" -ExternalPreauthentication ADFS -ExternalUrl https://ContosoApp.Contoso.com/ -ExternalCertificateThumbprint "69DF0AB8434060DC869D37BBAEF770ED5DD0C32A" -BackendServerUrl http://ContosoApp:8080/ -ADFSRelyingPartyName "ContosoAppRP"
```

This command publishes a web application that specifies the value of AD FS for the **ExternalPreauthentication** parameter.

### Example 2: Publish a web application that omits external preauthentication
```
PS C:\> Add-WebApplicationProxyApplication -Name "ContosoApp" -BackendServerUrl http://ContosoApp/ -ExternalUrl https://ContosoApp.Contoso.com/ -ExternalPreauthentication "PassThrough" -ExternalCertificateThumbprint "D1A657E1A4F276FCC45613C0F6B3BC91AFC4633F"
```

This command publishes a web application named ContosoApp.
The command specifies a backend server URL and an external URL.
The application uses pass-through preauthentication.

### Example 3: Publish an Exchange Active Sync application
```
PS C:\>Add-WebApplicationProxyApplication -BackendServerAuthenticationSPN 'HTTP/EXCH1.contoso.com' -BackendServerUrl 'https://extmail.contoso.com/Microsoft-Server-ActiveSync/' -ExternalCertificateThumbprint '27A3F96517C27443207BBFE94FA65E1B154170BB' -EnableHTTPRedirect -ExternalUrl 'https://extmail.contoso.com/Microsoft-Server-ActiveSync/' -Name 'ActiveSync' -ExternalPreAuthentication ADFSforRichClients -ADFSRelyingPartyName 'ActiveSync' -ADFSUserCertificateStore 'Root'
```

This command publishes an Exchange Active Sync application.
The application uses Integrated Windows Authentication with (IWA) Kerberos Constrained Delegation (KCD).

## PARAMETERS

### -ADFSRelyingPartyName
Specifies the name of the relying party configured on the AD FS federation server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: RPName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ADFSUserCertificateStore
Specifies the certificate store for a AD FS user.

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

### -BackendServerAuthenticationSPN
Specifies the service principal name (SPN) of the backend server.
Use this parameter if the application that the backend server hosts uses Integrated Windows authentication.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SPN

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -BackendServerCertificateValidation
Specifies whether Web Application Proxy validates the certificate that the backend server presents with the WAP configuration per application.
The acceptable values for this parameter are:

- None
- ValidateCertificate

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: None, ValidateCertificate

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -BackendServerUrl
Specifies the backend address of the web application.
Specify by protocol and host name or IP address.
Include the trailing slash (/).
You can also include a port number and path.
The following examples show the form of an address:

- http://AccountingApp.Contoso.com/
- http://Mail.Contoso.com/Remote/
- http://Portal/

```yaml
Type: String
Parameter Sets: (All)
Aliases: BackendUrl

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -ClientCertificateAuthenticationBindingMode
If this parameter is set to **ValidateCertificate** then the browser sends a certificate with each request and validates that the device certificate thumbprint from the certificate is included in the token or the cookie.
The acceptable values for this parameter are:

- None
- ValidateCertificate

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: None, ValidateCertificate

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClientCertificatePreauthenticationThumbprint
Specifies the certificate thumbprint, as a string, of the certificate that a client supplies for the preauthentication feature.
The thumbprint is 40 hexadecimal characters.
This parameter is only relevant when you specify the value of ClientCertificate for the **ExternalPreauthentication** parameter.

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

### -DisableHttpOnlyCookieProtection
Indicates that this cmdlet disables the use of the HttpOnly flag when Web Application Proxy sets the access cookie.
The access cookie provides single sign-on access to an application.

Important: by default, HttpOnly is enabled to help ensure network protection.
If you disable HttpOnly flag protection, the browser may share this cookie with other components on the client device, such as ActiveX, Java Applets and JavaScript, so they can access this application without the need to perform additional preauthentication.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisableTranslateUrlInRequestHeaders
Indicates that Web Application Proxy does not translate HTTP host headers from public host headers to internal host headers when it forwards the request to the published application.

Specify this parameter if the application uses path-based information.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisableTranslateUrlInResponseHeaders
Indicates that Web Application Proxy does not translate internal host names to public host names in **Content-Location**, **Location**, and **Set-Cookie** response headers in redirect responses.

If the proxy does not translate host names in the **Content-Location** or **Location** response headers, subsequent client requests resolve incorrectly.
If the proxy does not translate the host name in the **Set-Cookie** response header, the published web application might not use cookies properly.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableHTTPRedirect
Indicates that this cmdlet enables HTTP redirect for Web Application Proxy.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableSignOut
Indicates whether to enable sign out for Web Application Proxy.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExternalCertificateThumbprint
Specifies the certificate thumbprint, as a string, of the certificate to use for the address specified by the **ExternalUrl** parameter.
The thumbprint is 40 hexadecimal characters.

The certificate must exist in the Local Computer or Local Personal certificate store.
You can use a simple certificate, a subject alternative name (SAN) certificate, or a wildcard certificate.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ExternalCert

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExternalPreauthentication
Specifies the preauthentication method that Web Application Proxy uses.
The acceptable values for this parameter are:

- ADFS
- ClientCertificate
- PassThrough
- ADFSforRichClients
- ADFSforOAuth
- ADFSforBrowsersAndOffice

```yaml
Type: String
Parameter Sets: (All)
Aliases: PreAuthN
Accepted values: PassThrough, ADFS, ClientCertificate, ADFSforRichClients, ADFSforOAuth, ADFSforBrowsersAndOffice

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExternalUrl
Specifies the external address, as a URL, for the web application.
Include the trailing slash (/).

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InactiveTransactionsTimeoutSec
Specifies the length of time, in seconds, until Web Application Proxy closes incomplete HTTP transactions.

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

### -Name
Specifies a friendly name for the published web application.

```yaml
Type: String
Parameter Sets: (All)
Aliases: FriendlyName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PersistentAccessCookieExpirationTimeSec
Specifies the expiration time, in seconds, for persistent access cookies.

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

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.
Do not specify a value for this parameter greater than 1.

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

### -UseOAuthAuthentication
Indicates that Web Application Proxy provides the URL of the federation server that performs Open Authorization (OAuth) when users connect to the application by using a Windows Store app.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Management.Automation.SwitchParameter

### System.UInt32

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Web Application Proxy Overview](https://technet.microsoft.com/en-us/library/dn280944.aspx)

[Publishing Internal Applications using Web Application Proxy](https://technet.microsoft.com/en-us/library/dn383650.aspx)

[Get-WebApplicationProxyApplication](./Get-WebApplicationProxyApplication.md)

[Remove-WebApplicationProxyApplication](./Remove-WebApplicationProxyApplication.md)

[Set-WebApplicationProxyApplication](./Set-WebApplicationProxyApplication.md)

