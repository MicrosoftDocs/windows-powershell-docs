---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.Proxy.dll-Help.xml
Module Name: WebApplicationProxy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/webapplicationproxy/install-webapplicationproxy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Install-WebApplicationProxy
---

# Install-WebApplicationProxy

## SYNOPSIS
Configures Web Application Proxy on the server.

## SYNTAX

```
Install-WebApplicationProxy -FederationServiceTrustCredential <PSCredential> -CertificateThumbprint <String>
 -FederationServiceName <String> [-HttpsPort <Int32>] [-TlsClientPort <Int32>] [-ForwardProxy <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Install-WebApplicationProxy** cmdlet configures Web Application Proxy on the current server.

The **FederationServiceName** parameter specifies the Federation Service that provides authentication for Web Application Proxy.
The **FederationServiceTrustCredential** parameter specifies the Active Directory Federation Services (AD FS) identity that is authorized to register new Federation server proxies.
The **CertificateThumbprint** parameter specifies the thumbprint of the certificate that Web Application Proxy uses to identify the server to users as a proxy for the Federation Service.
You can also specify the name of a forward proxy, the HTTPS port for the Web Application Proxy server, and the port for the Transport Layer Security (TLS) client.

## EXAMPLES

### Example 1: Configure Web Application Proxy on the server
```
PS C:\> $FScredential = Get-Credential
PS C:\> Install-WebApplicationProxy -FederationServiceName "FS01.Contoso.com" -FederationServiceTrustCredential $FScredential -CertificateThumbprint "0a1b2c3d0a1b2c3d0a1b2c3d0a1b2c3d0a1b2c3d"
```

This example configures Web Application Proxy on the local server.

The first command uses the **Get-Credential** cmdlet to create a credential, and then stores it in the **$FScredential** variable.
The cmdlet prompts you for a user name and password.
For more information, type `Get-Help Get-Credential`.

The second command configures Web Application Proxy on the local server.
The command specifies the name of the Federation Service for which Web Application Proxy provides an AD FS proxy.
The command specifies the thumbprint of the certificate that Web Application Proxy presents to users to identify the Web Application Proxy server as a proxy for the Federation Service.

## PARAMETERS

### -CertificateThumbprint
Specifies the certificate thumbprint, as a string, of the certificate that Web Application Proxy presents to users to identify the Web Application Proxy as a proxy for the Federation Service.
The thumbprint is 40 hexadecimal characters.

The certificate must be in the Personal store for the local computer.
You can use a simple certificate, a subject alternative name (SAN) certificate, or a wildcard certificate.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FederationServiceName
Specifies the name of a Federation Service.
This is the Federation Service for which Web Application Proxy provides AD FS proxy functionality and stores the configuration of the Federation Service.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FederationServiceTrustCredential
Specifies a **PSCredential** object that contains the credentials of the AD FS identity that is authorized to register new Federation server proxies.
Specify an account that has permissions to manage the Federation Service.

To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type `Get-Help Get-Credential`.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForwardProxy
Specifies the DNS name and port number of an HTTP proxy that this federation server proxy uses to obtain access to the federation service.
Specify the value for this parameter in the following format: FQDN:PortNumber.
For example, to specify a forward proxy with a host name of "proxy01" that is located within the corp.contoso.com domain and that can be reached using the HTTP port of 8080 would be "proxy-01.corp.contoso.com:8080".
Note: This parameter applies only to Federation Services proxy.
It does not apply for application publishing.

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

### -HttpsPort
Specifies the HTTPS port for the Web Application Proxy server.
The default value is 443.

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

### -TlsClientPort
Specifies the port for the TLS client.
Web Application Proxy uses this port for user certificate authentication.
The default value is 49443.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Add-WebApplicationProxyApplication](./Add-WebApplicationProxyApplication.md)

[Get-WebApplicationProxyApplication](./Get-WebApplicationProxyApplication.md)

[Get-WebApplicationProxyConfiguration](./Get-WebApplicationProxyConfiguration.md)

[Set-WebApplicationProxyConfiguration](./Set-WebApplicationProxyConfiguration.md)

