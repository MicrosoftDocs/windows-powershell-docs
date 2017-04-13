---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: brianlic
author: brianlic-msft
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-AdfsProperties
ms.assetid: E9015DB1-D7C5-456C-87E6-18A9448F1AC7
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

	Get-AdfsProperties
	Microsoft.IdentityServer.Management.Resources.ServiceProperties
	{get;}         AcceptableIdentifiers                             uri[]
	{get;}         AddProxyAuthorizationRules                        string
	{get;}         AllowLocalAdminsServiceAdministration             bool
	{get;}         AllowSystemServiceAdministration                  bool
	{get;}         ArtifactDbConnection                              string
	{get;}         AuditLevel                                        string[]
	{get;}         AuthenticationContextOrder                        uri[]
	{get;}         AutoCertificateRollover                           bool
	{get;}         BrowserSsoEnabled                                 bool
	{get;}         BrowserSsoSupportedUserAgents                     string[]
	{get;}         CertificateCriticalThreshold                      int
	{get;}         CertificateDuration                               int
	{get;}         CertificateGenerationThreshold                    int
	{get;}         CertificatePromotionThreshold                     int
	{get;}         CertificateRolloverInterval                       int
	{get;}         CertificateSharingContainer                       string
	{get;}         CertificateThresholdMultiplier                    int
	{get;}         ClientCertRevocationCheck                         Microsoft.IdentityServer.PolicyModel.Configuration.RevocationSetting
	{get;}         ContactPerson                                     Microsoft.IdentityServer.Management.Resources.ContactPerson
	{get;}         CurrentFarmBehavior                               int
	{get;}         DelegateServiceAdministration                     string
	{get;}         DeviceUsageWindowInDays                           int
	{get;}         DisplayName                                       string
	{get;}         EnableIdpInitiatedSignonPage                      bool
	{get;}         EnableOauthLogout                                 bool
	{get;}         ExtendedProtectionTokenCheck                      Microsoft.IdentityServer.PolicyModel.Configuration.ProtectionPolicySetting
	{get;}         ExtranetLockoutEnabled                            bool
	{get;}         ExtranetLockoutRequirePDC                         bool
	{get;}         ExtranetLockoutThreshold                          int
	{get;}         ExtranetObservationWindow                         timespan
	{get;}         FederationPassiveAddress                          string
	{get;}         GlobalRelyingPartyClaimsIssuancePolicy            string
	{get;}         HostName                                          string
	{get;}         HttpPort                                          int
	{get;}         HttpsPort                                         int
	{get;}         Identifier                                        uri
	{get;}         IdTokenIssuer                                     uri
	{get;}         IgnoreTokenBinding                                bool
	{get;}         InstalledLanguage                                 string
	{get;}         IntranetUseLocalClaimsProvider                    bool
	{get;}         KmsiEnabled                                       bool
	{get;}         KmsiLifetimeMins                                  int
	{get;}         LocalAuthenticationTypesEnabled                   bool
	{get;}         LogLevel                                          string[]
	{get;}         LoopDetectionEnabled                              bool
	{get;}         LoopDetectionMaximumTokensIssuedInInterval        int
	{get;}         LoopDetectionTimeIntervalInSeconds                int
	{get;}         MonitoringInterval                                int
	{get;}         NetTcpPort                                        int
	{get;}         NtlmOnlySupportedClientAtProxy                    bool
	{get;}         OrganizationInfo                                  Microsoft.IdentityServer.Management.Resources.Organization
	{get;}         PasswordValidationDelayInMinutes                  int
	{get;}         PersistentSsoCutoffTime                           datetime
	{get;}         PersistentSsoEnabled                              bool
	{get;}         PersistentSsoLifetimeMins                         int
	{get;}         PreventTokenReplays                               bool
	{get;}         ProxyTrustTokenLifetime                           int
	{get;}         RelayStateForIdpInitiatedSignOnEnabled            bool
	{get;}         ReplayCacheExpirationInterval                     int
	{get;}         SamlMessageDeliveryWindow                         int
	{get;}         SendClientRequestIdAsQueryStringParameter         bool
	{get;}         SignedSamlRequestsRequired                        bool
	{get;}         SignSamlAuthnRequests                             bool
	{get;}         SsoLifetime                                       int
	{get;}         TlsClientPort                                     int
	{get;}         WiaEvaluationMethod                               Microsoft.IdentityServer.WiaEvaluationMethodState
	{get;}         WIASupportedUserAgents                            string[]
	---------------------------
	
	
	
	Microsoft.IdentityServer.PolicyModel.Configuration.RevocationSetting
	public enum RevocationSetting
	    {
	        None = 0,
	        CheckEndCert = 1,
	        CheckEndCertCacheOnly = 2,
	        CheckChain = 3,
	        CheckChainCacheOnly = 4,
	        CheckChainExcludeRoot = 5,
	        CheckChainExcludeRootCacheOnly = 6,
	    }
	
	---------------------------
	
	
	
	Microsoft.IdentityServer.Management.Resources.ContactPerson
	{get;}       ContactType                       string
	{get;}       EmailAddresses                    string[]
	{get;}       GivenName                         string
	{get;}       PhoneNumbers                      string[]
	{get;}       Surname                           string
	---------------------------
	
	
	
	(Get-AdfsProperties | select ExtendedProtectionTokenCheck)
	public static class ProtectionPolicySetting
	        {
	            public const string Allow = "Allow";
	            public const string Require = "Require";
	            public const string None = "None";
	        }
	---------------------------
	
	
	
	Microsoft.IdentityServer.Management.Resources.Organization
	{get;}       DisplayName                       string
	{get;}       Name                              string
	{get;}       OrganizationUrl                   string
	---------------------------
	
	
	
	(Get-AdfsProperties | select WIASupportedUserAgents)
	public enum WiaEvaluationMethodState
	    {
	        WiaCapabilityDetection,
	        WiaUserAgentDetection
	    }
	---------------------------

## NOTES

## RELATED LINKS

[Set-AdfsProperties](./Set-AdfsProperties.md)

