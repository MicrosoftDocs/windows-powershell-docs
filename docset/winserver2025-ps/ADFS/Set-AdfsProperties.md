---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 10/02/2017
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfsproperties?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsProperties
---

# Set-AdfsProperties

## SYNOPSIS
Sets the properties that control global behaviors in AD FS.

## SYNTAX

```
Set-AdfsProperties [-AuthenticationContextOrder <Uri[]>] [-AcceptableIdentifiers <Uri[]>]
 [-AddProxyAuthorizationRules <String>] [-ArtifactDbConnection <String>] [-AuditLevel <String[]>]
 [-AutoCertificateRollover <Boolean>] [-CertificateCriticalThreshold <Int32>] [-CertificateDuration <Int32>]
 [-CertificateGenerationThreshold <Int32>] [-CertificatePromotionThreshold <Int32>]
 [-CertificateRolloverInterval <Int32>] [-CertificateThresholdMultiplier <Int32>]
 [-ClientCertRevocationCheck <String>] [-ContactPerson <ContactPerson>] [-DisplayName <String>]
 [-EnableOAuthDeviceFlow <Boolean>]
 [-EnableOAuthLogout <Boolean>] [-FederationPassiveAddress <String>] [-HostName <String>] [-HttpPort <Int32>]
 [-HttpsPort <Int32>] [-IntranetUseLocalClaimsProvider <Boolean>] [-TlsClientPort <Int32>] [-Identifier <Uri>]
 [-LogLevel <String[]>] [-MonitoringInterval <Int32>] [-NetTcpPort <Int32>]
 [-NtlmOnlySupportedClientAtProxy <Boolean>] [-OrganizationInfo <Organization>]
 [-PreventTokenReplays <Boolean>] [-ExtendedProtectionTokenCheck <String>] [-ProxyTrustTokenLifetime <Int32>]
 [-ReplayCacheExpirationInterval <Int32>] [-SignedSamlRequestsRequired <Boolean>]
 [-SamlMessageDeliveryWindow <Int32>] [-SignSamlAuthnRequests <Boolean>] [-SsoLifetime <Int32>]
 [-SsoEnabled <Boolean>] [-PersistentSsoLifetimeMins <Int32>] [-KmsiLifetimeMins <Int32>]
 [-EnablePersistentSso <Boolean>] [-PersistentSsoCutoffTime <DateTime>] [-EnableKmsi <Boolean>]
 [-WIASupportedUserAgents <String[]>] [-BrowserSsoSupportedUserAgents <String[]>]
 [-BrowserSsoEnabled <Boolean>] [-LoopDetectionTimeIntervalInSeconds <Int32>]
 [-LoopDetectionMaximumTokensIssuedInInterval <Int32>] [-EnableLoopDetection <Boolean>] [-ExtranetLockoutMode <String>]
 [-ExtranetLockoutThreshold <Int32>] [-EnableExtranetLockout <Boolean>] [-ExtranetObservationWindow <TimeSpan>]
 [-ExtranetLockoutRequirePDC <Boolean>] [-SendClientRequestIdAsQueryStringParameter <Boolean>]
 [-GlobalRelyingPartyClaimsIssuancePolicy <String>] [-EnableLocalAuthenticationTypes <Boolean>]
 [-EnableRelayStateForIdpInitiatedSignOn <Boolean>] [-DelegateServiceAdministration <String>]
 [-AllowSystemServiceAdministration <Boolean>] [-AllowLocalAdminsServiceAdministration <Boolean>]
 [-DeviceUsageWindowInDays <Int32>] [-EnableIdPInitiatedSignonPage <Boolean>] [-IgnoreTokenBinding <Boolean>]
 [-IdTokenIssuer <Uri>] [-PromptLoginFederation <PromptLoginFederation>]
 [-PromptLoginFallbackAuthenticationType <String>] [-Force] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsProperties** cmdlet sets the properties that control global behaviors in Active Directory Federation Services (AD FS).

## EXAMPLES

### Example 1: Set the ADFS properties
```
PS C:\> $Timespan = New-TimeSpan -Minutes 60
PS C:\> Set-AdfsProperties -EnableExtranetLockout $True -ExtranetLockoutThreshold 4 -ExtranetObservationWindow $Timespan
```

The first command creates a **TimsSpan** object and stores the result in the variable named $Timespan.

The second command sets an extranet lockout algorithm with a threshold of 4 max bad password attempts before lockout.
The command also sets the observation window for the value stored in the $Timespan variable.

## PARAMETERS

### -AcceptableIdentifiers
Specifies an array of identifiers that are acceptable names for the Federation Service when it checks the audience for claims that it receives from another claims provider.

```yaml
Type: Uri[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddProxyAuthorizationRules
This parameter is deprecated.

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

### -AllowLocalAdminsServiceAdministration
Indicates that local administrator service administration is allowed.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowSystemServiceAdministration
Indicates that system service administration is allowed.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ArtifactDbConnection
Specifies the connection string to use for the database that maintains the artifacts that the artifact resolution service uses.

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

### -AuditLevel
Specifies an array of audit levels.
The acceptable values for this parameter are:

- None
- Basic
- Verbose

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:
Accepted values: None, Basic, Verbose

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthenticationContextOrder
Specifies an array of authentication contexts, in order of relative strength.
Specify each authentication context as a URI.

```yaml
Type: Uri[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutoCertificateRollover
Indicates whether the system manages certificates for the administrator and generates new certificates before the expiration date of current certificates.
By default, this setting is enabled for a new instance of AD FS.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BrowserSsoEnabled
Indicates that browser single sign-on (SSO) is enabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BrowserSsoSupportedUserAgents
Specifies an array of user agents that are supported for browser SSO.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateCriticalThreshold
Specifies the period of time, in days, prior to the expiration of a current primary signing or decryption certificate.
When a certificate reaches this threshold, the Federation Service initiates the automatic certificate rollover service, generates a new certificate, and promotes it as the primary certificate.
This rollover process occurs even if the critical threshold interval does not provide sufficient time for partners to replicate the new metadata.
Specify a short period of time that is used only in extreme conditions when the Federation Service has not been able to generate a new certificate in advance.

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

### -CertificateDuration
Specifies the period of time, in days, that any certificates that the Federation Service generates remain valid.

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

### -CertificateGenerationThreshold
Specifies the period of time, in days, before the Federation Service generates a new primary certificate to replace the current primary certificate.
When a certificate reaches this threshold, the Federation Service initiates an automatic certificate rollover process that generates a new certificate and adds it to the secondary collection.
This rollover process occurs so that federation partners can consume this metadata in advance and trust is not broken when this newly generated certificate is promoted to be a primary certificate.

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

### -CertificatePromotionThreshold
Specifies the period of time, in days, during which a newly generated certificate remains a secondary certificate before being promoted as the primary certificate.

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

### -CertificateRolloverInterval
Specifies the certificate rollover interval, in minutes.
This value determines the frequency at which the Federation Service initiates the rollover service by polling to check whether new certificates need to be generated.

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

### -CertificateThresholdMultiplier
Specifies the certificate threshold multiplier.
By default, this parameter uses the number of minutes in a day (1440) as a multiplier.
Change this value only if you want to use a more finely detailed measure of time, such as less than a single day, for calculating the time periods for other certificate threshold parameters.

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

### -ClientCertRevocationCheck
Do not use this parameter.
Instead, use the `netsh http` command to configure certificate settings.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: CheckChain, CheckChainCacheOnly, CheckChainExcludeRoot, CheckChainExcludeRootCacheOnly, CheckEndCert, CheckEndCertCacheOnly, None

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContactPerson
Specifies the contact information for support issues.

```yaml
Type: ContactPerson
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DelegateServiceAdministration
Specifies the delegate service administration.

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

### -DeviceUsageWindowInDays
Specifies the length of the device usage window in days.

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

### -DisplayName
Specifies a friendly name for the Federation Service.

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

### -EnableExtranetLockout
Indicates whether to enable the lockout algorithm for extranet.
When enabled, AD FS checks attributes in Active Directory for the user before validating the credential.
If the user is determined to be in lockout state, AD FS will deny the request to the user when accessing from the extranet, to prevent random login attempts from the extranet.
Intranet access will continue to be validated against Active Directory.
By default, this feature is disabled in a new instance of AD FS and must be explicitly enabled by the administrator.

When this feature is enabled AD FS must be able to contact the Primary Domain Controller (PDC) of the user's domain.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableIdPInitiatedSignonPage
Specifies whether to enable the **EnableIdPInitiatedSignonPage** property.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableKmsi
Indicates whether to enable the Keep Me Signed In (KMSI) option for form-based authentication.
KMSI is limited to providing only 24 hours of SSO.
Note that a workplace joined device gets 7 days of SSO by default and does not need this option enabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableLocalAuthenticationTypes
Indicates that local authentication types are enabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableLoopDetection
Indicates whether to enable loop detection.
Loops occur when a relying party continuously rejects a valid security token and redirects back to AD FS.
The cycle terminates after 6 loops have been detected.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableOAuthDeviceFlow
Enables the OAuth Device Flow.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableOAuthLogout
Enables the OAuth logout endpoint publishing in the OAuth discovery document. The OAuth logout endpoint logs out the current user from the AD FS. This parameter is available with the Windows Update KB4019472 installed. The AD FS does not support logging out a federated user from the federated identity provider when using the OAuth logout endpoint with Windows Update KB4019472 installed. The Windows Update KB4038801 makes this parameter obsolete and the value of this parameter to be always true. The Windows Update KB4038801 also adds support for logging our a federated user from the federated identity provider when using the OAuth logout endpoint.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnablePersistentSso
Indicates whether to store the SSO token in persistent cookies for devices joined to a workplace.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableRelayStateForIdpInitiatedSignOn
Indicates that relay state for issuing distribution point (IDP) initiated sign-on is enabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtendedProtectionTokenCheck
Specifies the level of extended protection for authentication supported by the federation server.
Extended Protection for Authentication helps protect against man-in-the-middle (MITM) attacks, in which an attacker intercepts a client's credentials and forwards them to a server.
Protection against such attacks is made possible through a Channel Binding Token (CBT) which can be either required, allowed or not required by the server when establishing communications with clients.

The acceptable values for this parameter are:

- Require.
Server is fully hardened, extended protection is enforced
- Allow.
Server is partially hardened, extended protection is enforced where systems involved have been patched to support it
- None.
Server is vulnerable, extended protection is not enforced

The default setting is Allow.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Allow, Require, None

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtranetLockoutMode:
Specifies Extranet Smart Lockout mode.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: ADPasswordCounter, ADFSSmartLockoutLogOnly, ADFSSmartLockoutEnforce

Required: False
Position: Named
Default value: ADPasswordCounter
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtranetLockoutRequirePDC
Specifies whether extranet lockout requires a primary domain controller (PDC).

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtranetLockoutThreshold
Specifies the maximum number of bad password attempts permitted against the directory before the account is throttled when accessing applications from the extranet.
If you use Active Directory® Domain Services account lockout policies, it is strongly recommended that you set this threshold to a value that is less than the threshold in AD DS to avoid lockout of the user inside and outside the network.

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

### -ExtranetObservationWindow
Specifies the timespan of the lockout observation window.
AD FS will reset a throttled state of an account when more than one observation window has expired since the last bad password attempt, as reported by Active Directory Domain Services.
It is also possible that the last bad password field in AD DS is cleared by AD DS based on its own observation windows.
In this case, AD FS will allow the request to be passed onto AD DS for validation.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FederationPassiveAddress
Do not use this parameter.

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

### -GlobalRelyingPartyClaimsIssuancePolicy
Specifies a global relying party claims issuance policy.

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

### -HostName
Specifies the network addressable host name of the Federation Service.

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

### -HttpPort
Specifies the HTTP port for the server.

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

### -HttpsPort
Specifies the HTTPS port for the server.

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

### -Identifier
Specifies the URI that uniquely identifies the Federation Service.

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

### -IdTokenIssuer
Specifies the URI of the token issuer.

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

### -IgnoreTokenBinding
Specifies whether to ignore token binding.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IntranetUseLocalClaimsProvider
Indicates whether all web based requests from the intranet default to the default Active Directory claims provider.
Use this parameter only when there is more than one claims provider trust in AD FS and you want all user access from the intranet to use the default Active Directory for authentication.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KmsiLifetimeMins
Specifies the lifetime of the sign on status for KMSI.

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

### -LogLevel
Specifies an array of log detail.
The array defines which types of events to record.
The acceptable values for this parameter are:

- Errors
- Warnings
- Information
- SuccessAudits
- FailureAudits

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:
Accepted values: Errors, FailureAudits, Information, Verbose, None, SuccessAudits, Warnings

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoopDetectionMaximumTokensIssuedInInterval
Specifies the maximum number of tokens that can be issued within the time period specified by the **LoopDetectionTimeIntervalInSeconds** parameter before AD FS will reject the request and present an error to the user.
Use in conjunction with the **LoopDetectionMaximumTokensIssuedInInterval** parameter.

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

### -LoopDetectionTimeIntervalInSeconds
Specifies the time interval in seconds for AD FS to track multiple token requests that are occurring and being rejected by the relying party causing a redirect back to AD FS for a new token request.
Use in conjunction with the *LoopDetectionMaximumTokensIssuedInInterval* parameter.

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

### -MonitoringInterval
Specifies the frequency, in minutes, with which the Federation Service monitors the federation metadata of relying parties and claims providers that are enabled for federation metadata monitoring.

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

### -NetTcpPort
Specifies the TCP port number for the server.

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

### -NtlmOnlySupportedClientAtProxy
Indicates whether to enable support for NTLM-based authentication in situations where the active federation server proxy does not support Negotiate method of authentication.
This setting only affects the Windows transport endpoint.
If this value is changed, the federation server proxy needs to be restarted.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OrganizationInfo
Specifies information about the organization as published in the federation metadata for the Federation Service.

```yaml
Type: Organization
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -PersistentSsoCutoffTime
Specifies the earliest issue time of accepted persistent single sign-on (SSO) tokens and OAuth refresh tokens.
Persistent SSO tokens or OAuth refresh tokens issued before this time will be rejected.
Use this only to reject all prior SSO state across all users and force users to provide fresh credentials.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PersistentSsoLifetimeMins
Specifies the duration, in minutes, of the persistent SSO experience.

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

### -PreventTokenReplays
Indicates whether the Federation Service prevents the replay of security tokens.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PromptLoginFallbackAuthenticationType

This parameter is obsolete. Please set this property on individual Claims Provider Trusts.

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

### -PromptLoginFederation

This parameter is obsolete. Please set this property on individual Claims Provider Trusts.

```yaml
Type: PromptLoginFederation
Parameter Sets: (All)
Aliases:
Accepted values: None, FallbackToProtocolSpecificParameters, ForwardPromptAndHintsOverWsFederation, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyTrustTokenLifetime
Specifies the valid token lifetime, in minutes, for proxy trust tokens.
This value is used by the federation server proxy to authenticate with its associated federation server.

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

### -ReplayCacheExpirationInterval
Specifies the cache duration, in minutes, for token replay detection.
This value determines the lifetime for tokens in the replay cache.
When the age of a cached token exceeds this interval, the Federation Service determines the token has expired and does not allow replay of it.

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

### -SamlMessageDeliveryWindow
Specifies the duration, in minutes, for which the Security Assertion Markup Language (SAML) messages sent by the Federation Service are considered valid.

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

### -SendClientRequestIdAsQueryStringParameter
Indicates whether the client request id, or activity id, is sent as a query string on any redirect from AD FS that is sent to itself.
This enables all servers in AD FS to use the same client request id when logging any messages in eventlogs, traces and audits.
As a result, it is easier to troubleshoot a single request across multiple AD FS servers in the farm.
The default value is $True.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignedSamlRequestsRequired
Indicates whether the Federation Service requires signed SAML protocol requests from the relying party.
If you specify a value of $True, the Federation Service rejects unsigned SAML protocol requests.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignSamlAuthnRequests
Indicates whether the Federation Service signs SAML protocol authentication requests to claims providers.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SsoEnabled
This parameter is deprecated.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SsoLifetime
Specifies the duration, in minutes, of the single sign-on (SSO) experience for Web browser clients.

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
Specifies the port number where AD FS listens for user certificate authentication requests.
Use this only when user certificate authentication is used in AD FS.

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

### -WIASupportedUserAgents
Specifies an array of acceptable user agents that support seamless sign-in with Windows Integrated Authentication.
If AD FS receives a token request  and  policy selects Windows Integrated Authentication, AD FS uses this list to determine if it needs to fall back to forms-based authentication.
When the user agent for the incoming request is not in this list, AD FS falls back to forms-based authentication.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### System.Object

## NOTES

## RELATED LINKS

[Get-AdfsProperties](./Get-AdfsProperties.md)
