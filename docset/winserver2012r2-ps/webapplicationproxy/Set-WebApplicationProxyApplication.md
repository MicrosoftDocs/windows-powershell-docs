---
external help file: WebApplicationProxy-help.xml
Module Name: WebApplicationProxy
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/webapplicationproxy/set-webapplicationproxyapplication?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WebApplicationProxyApplication
---

# Set-WebApplicationProxyApplication

## SYNOPSIS
Modifies settings of a web application published through Web Application Proxy.

## SYNTAX

```
Set-WebApplicationProxyApplication [-ClientCertificateAuthenticationBindingMode <String>]
 [-BackendServerCertificateValidation <String>] [-ExternalUrl <Uri>] [-ExternalCertificateThumbprint <String>]
 [-BackendServerUrl <Uri>] [-DisableTranslateUrlInRequestHeaders] [-DisableTranslateUrlInResponseHeaders]
 [-BackendServerAuthenticationSPN <String>] [-Name <String>] [-UseOAuthAuthentication]
 [-InactiveTransactionsTimeoutSec <UInt32>] [-ClientCertificatePreauthenticationThumbprint <String>]
 [-ID] <Guid> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WebApplicationProxyApplication** cmdlet modifies settings of a web application published through Web Application Proxy.
Specify the web application to modify by using its ID.
Note that the method of pre-authentication cannot be changed.
The cmdlet ensures that no other applications are already configured to use any specified **ExternalURL** or **BackendServerURL**.

## EXAMPLES

### Example 1: Change the extern URL for a web application
```
PS C:\>Set-WebApplicationProxyApplication -ID 874A4543-7983-77A3-1E6D-1163E7419AC1 -ExternalUrl https://SP.Contoso.com/
```

This command changes the external URL to https://sp.contoso.com/ for the web application that has the specified ID.

### Example 2: Change the backend server URL and the external URL
```
PS C:\>Set-WebApplicationProxyApplication -ID 874A4543-7983-77A3-1E6D-1163E7419AC1 -BackendServerUrl https://Portal.Contoso.com/ -ExternalUrl https://SP.Contoso.com/
```

This command modifies a web application that has the specified ID.
The command changes the backend server to be https://Portal.Contoso.com/ and the external URL to be https://SP.Contoso.com/.

### Example 3: Change the name of a web application
```
PS C:\>Set-WebApplicationProxyApplication -ID 874A4543-7983-77A3-1E6D-1163E7419AC1 -Name Test123
```

This command changes the friendly name of an application that has the specified ID.

### Example 4: Disable URL translation in headers
```
PS C:\>Set-WebApplicationProxyApplication -ID 874A4543-7983-77A3-1E6D-1163E7419AC1 -DisableTranslateUrlInRequestHeaders -DisableTranslateUrlInResponseHeaders
```

This command modifies the web application that has the specified ID.
The command disables URL translation in both request and response headers.

### Example 5: Change the certificate thumbprint for a web application
```
PS C:\>Set-WebApplicationProxyApplication -ID 874A4543-7983-77A3-1E6D-1163E7419AC1 -ExternalCertificateThumbprint FFAFA2422D77BC784D1F48E08F6BDAE32CD109A2
```

This command changes the external certificate thumbprint for the web application that has the specified ID.

### Example 6: Change the timeout interval for web applications
```
PS C:\>Get-WebApplicationProxyApplication SharePoint* | Set-WebApplicationProxyApplication -InactiveTransactionsTimeoutSec 400
```

This command changes the inactive transaction timeout for all web applications whose names begin with the string SharePoint.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Specifies the SPN of the backend server.
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
Specifies whether Web Application Proxy validates the certificate that the backend server presents.
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
Specifies the address of the web application.
Specify the protocol and host name or IP address.
Include the trailing slash (/).
You can also include a port number and path.
The following examples show the form of an address: 

- http://AccountingApp.Contoso.com/
- http://Mail.Contoso.com/Remote/
- http://Portal/

The cmdlet checks that no other applications are already configured to use this URL.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: BackendUrl

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
Specifies whether Web Application Proxy verifies whether the certificate that authenticates the federation server authenticates future requests.
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

### -DisableTranslateUrlInRequestHeaders
Indicates that Web Application Proxy does not translate HTTP host headers from public host headers to internal host headers when it forwards the request to the published application.

Specify this parameter if the application uses path-based information.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
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
Default value: False
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

### -ExternalUrl
Specifies the external address, as a URL, for the web application.
Include the trailing slash (/).

The cmdlet checks that no other applications are already configured to use this URL.

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

### -ID
Specifies the GUID of a web application.
To obtain the GUID of a web application, use the Get-WebApplicationProxyApplication cmdlet.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: ApplicationID

Required: True
Position: 0
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
Default value: 300
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a friendly name for the published web application.

```yaml
Type: String
Parameter Sets: (All)
Aliases: FriendlyName

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
Default value: 1
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
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Web Application Proxy Overview](https://technet.microsoft.com/library/dn280944.aspx)

[Publishing Internal Applications using Web Application Proxy](https://technet.microsoft.com/library/dn383650.aspx)

[Add-WebApplicationProxyApplication](./Add-WebApplicationProxyApplication.md)

[Get-WebApplicationProxyApplication](./Get-WebApplicationProxyApplication.md)

[Remove-WebApplicationProxyApplication](./Remove-WebApplicationProxyApplication.md)

