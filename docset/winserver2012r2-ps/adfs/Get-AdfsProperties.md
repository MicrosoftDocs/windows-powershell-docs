---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/adfs/get-adfsproperties?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AdfsProperties
---

# Get-AdfsProperties

## SYNOPSIS
Gets all the associated properties for the AD FS service.

## SYNTAX

```
Get-AdfsProperties [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsProperties** cmdlet gets all the associated properties for the Active Directory Federation Services (AD FS) service.

## EXAMPLES

### Example 1: Get the associated properties
```
PS C:\> Get-AdfsProperties


AcceptableIdentifiers                      : {}
AddProxyAuthorizationRules                 : exists([Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/groupsid", Value == "S-1-5-32-544", Issuer =~ "^AD AUTHORITY$"]) =>
issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");
c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid", Issuer =~ "^AD AUTHORITY$" ]
=>
issue(store="_ProxyCredentialStore",types=("http://schemas.microsoft.com/authorization/claims/permit"),query="isProxyTrustManagerSid({0})",
param=c.Value );
c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/proxytrustid", Issuer =~ "^SELF AUTHORITY$" ]
=>
issue(store="_ProxyCredentialStore",types=("http://schemas.microsoft.com/authorization/claims/permit"),query="isProxyTrustProvisioned({0})",
param=c.Value );
ArtifactDbConnection                       : Data Source=np:\\.\pipe\microsoft##wid\tsql\query;Initial Catalog=AdfsArtifactStore;Integrated Security=True
AuthenticationContextOrder                 : {urn:oasis:names:tc:SAML:2.0:ac:classes:Password, urn:oasis:names:tc:SAML:2.0:ac:classes:PasswordProtectedTransport,
urn:oasis:names:tc:SAML:2.0:ac:classes:TLSClient, urn:oasis:names:tc:SAML:2.0:ac:classes:X509...}
AutoCertificateRollover                    : False
CertificateCriticalThreshold               : 2
CertificateDuration                        : 365
CertificateGenerationThreshold             : 20
CertificatePromotionThreshold              : 5
CertificateRolloverInterval                : 720
CertificateSharingContainer                : CN=e6ddcbbc-5dc9-4ef2-9354-5e9ba1cac82d,CN=ADFS,CN=Microsoft,CN=Program Data,DC=contoso,DC=com
CertificateThresholdMultiplier             : 1440
ClientCertRevocationCheck                  : None
ContactPerson                              : Microsoft.IdentityServer.Management.Resources.ContactPerson
DisplayName                                : Contoso Corp.
IntranetUseLocalClaimsProvider             : False
ExtendedProtectionTokenCheck               : Allow
FederationPassiveAddress                   : /adfs/ls/
HostName                                   : sts.contoso.com
HttpPort                                   : 80
HttpsPort                                  : 443
TlsClientPort                              : 49443
Identifier                                 : http://sts.contoso.com/adfs/services/trust
InstalledLanguage                          : en-US
LogLevel                                   : {Errors, Information, Verbose, Warnings}
MonitoringInterval                         : 1440
NetTcpPort                                 : 1501
NtlmOnlySupportedClientAtProxy             : True
OrganizationInfo                           :
PreventTokenReplays                        : False
ProxyTrustTokenLifetime                    : 21600
ReplayCacheExpirationInterval              : 60
SignedSamlRequestsRequired                 : False
SamlMessageDeliveryWindow                  : 5
SignSamlAuthnRequests                      : False
SsoLifetime                                : 480
PersistentSsoLifetimeMins                  : 10080
PersistentSsoEnabled                       : True
PersistentSsoCutoffTime                    : 1/1/0001 12:00:00 AM
KmsiEnabled                                : False
LoopDetectionEnabled                       : True
LoopDetectionTimeIntervalInSeconds         : 20
LoopDetectionMaximumTokensIssuedInInterval : 5
SendClientRequestIdAsQueryStringParameter  : True
WIASupportedUserAgents                     : {MSIE 6.0, MSIE 7.0, MSIE 8.0, MSIE 9.0...}
ExtranetLockoutThreshold                   : 2
ExtranetLockoutEnabled                     : True
ExtranetObservationWindow                  : 01:00:00
```

This command retrieves the associated properties from AD FS.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Set-AdfsProperties](./Set-AdfsProperties.md)

