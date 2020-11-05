---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
ms.assetid: 2AA5563E-A075-4C54-909F-5C7B50D652A9
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Set-ADFSConfiguration

## SYNOPSIS
Sets the configuration properties of the Federation Service.

## SYNTAX

```
Set-ADFSConfiguration [-AuthenticationContextOrder <Uri[]>] [-AcceptableIdentifiers <Uri[]>]
 [-AddProxyAuthorizationRules <String>] [-ArtifactDbConnection <String>] [-AutoCertificateRollover <Boolean>]
 [-CertificateCriticalThreshold <Int32>] [-CertificateDuration <Int32>]
 [-CertificateGenerationThreshold <Int32>] [-CertificatePromotionThreshold <Int32>]
 [-CertificateRolloverInterval <Int32>] [-CertificateThresholdMultiplier <Int32>]
 [-ClientCertRevocationCheck <String>] [-ContactPerson <ContactPerson>] [-DisplayName <String>]
 [-FederationPassiveAddress <String>] [-HostName <String>] [-HttpPort <Int32>] [-HttpsPort <Int32>]
 [-Identifier <Uri>] [-LogLevel <String[]>] [-MonitoringInterval <Int32>] [-NetTcpPort <Int32>]
 [-NtlmOnlySupportedClientAtProxy <Boolean>] [-OrganizationInfo <Organization>]
 [-PreventTokenReplays <Boolean>] [-ExtendedProtectionTokenCheck <String>] [-ProxyTrustTokenLifetime <Int32>]
 [-ReplayCacheExpirationInterval <Int32>] [-SignedSamlRequestsRequired <Boolean>]
 [-SamlMessageDeliveryWindow <Int32>] [-SignSamlAuthnRequests <Boolean>] [-SsoLifetime <Int32>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Set-ADFSConfiguration cmdlet sets the global properties and configuration of the Federation Service.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\>Set-ADFSConfiguration -DisplayName "Fabrikam STS" -Identifier "https://fabrikam.com"
```

Sets the identifier for the Federation Service named "Fabrikam STS".

### -------------------------- EXAMPLE 2 --------------------------
```
PS C:\>Set-ADFSProperties -HttpPort 8123
```

Sets the HTTP port to 8123. 

Before restarting the Federation service, update the ACLs for the corresponding endpoint URLs to ensure that the service can be restarted successfully using the new port numbers.
For example, use a Netsh command similar to the following example to add the required ACL for the updated URL.

`netsh http addurlacl url=http://+:8123/adfs/services/ -user "Network Service"`

## PARAMETERS

### -AcceptableIdentifiers
Specifies identifiers that are acceptable names for the Federation Service when it checks the audience for claims that it receives from another claims provider.

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
Specifies a policy rule set that can be used to establish authorization permissions for setting up trust proxies.
The default value allows the AD FS service user account or any member of BUILTIN\Administrators to register a federation server proxy with the Federation Service.
Modifying this property should only be done if you want to enable another account beyond those accounts authorized by default to enable federation server proxies.
If the authorization rules you add are configured incorrectly, you can potentially disable registering new proxies.

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

### -AuthenticationContextOrder
Specifies a list of authentication contexts, in order by relative strength.
Each authentication context must be a URI.

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
Specifies whether the system will manage certificates for the administrator and generate new certificates before the expiration date of current certificates.

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

### -CertificateCriticalThreshold
Specifies the period of time (in days) before a current primary signing or decryption certificate expires.
When this threshold occurs, the Federation Service initiates the auto-rollover service, generates a new certificate, and promotes it to be the primary certificate.
This rollover process occurs even if the critical threshold interval does not provide sufficient time for partners to replicate the new metadata.
This should be a short period of time that is used only in extreme conditions when the Federation Service has not been able to generate a new certificate in advance.

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
Specifies the period of time (in days) that any certificates that the Federation Service generates remain valid.

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
Specifies the period of time (in days) before a new primary certificate is generated to replace the current primary certificate.
When this threshold occurs, the Federation Service initiates an auto-rollover process that generates a new certificate and adds it to the secondary collection.
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
Specifies the period of time (in days) during which a newly generated certificate remains a secondary certificate before being promoted to be the primary certificate.

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
Specifies the certificate rollover interval (in minutes).
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
This should be changed only if you want to use a more finely detailed measure of time (such as less than a single day) for calculating the time periods for other certificate threshold parameters in this cmdlet.

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
Specifies the type of validation that should occur for the client encryption certificate before it is used for decrypting claims from a claims provider.
Valid values are None, CheckEndCert, CheckEndCertCacheOnly, CheckChain, CheckChainCacheOnly, CheckChainExcludingRoot, and CheckChainExcludingRootCacheOnly.

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

### -ContactPerson
Specifies contact information for support.

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

### -DisplayName
Specifies the friendly name for this Federation Service.

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

### -ExtendedProtectionTokenCheck
Specifies the level of extended protection for authentication supported by the federation server.
Extended Protection for Authentication helps protect against man-in-the-middle (MITM) attacks, in which an attacker intercepts a client's credentials and forwards them to a server.
Protection against such attacks is made possible through a Channel Binding Token (CBT) which can be either required, allowed or not required by the server when establishing communications with clients.

Possible values for this setting are: as follows "Require" (server is full hardened, extended protection is enforced), "Allow" (server is partially hardened, extended protection is enforced where systems involved have been patched to support it) and "None" (Server is vulnerable, extended protection is not enforced).
The default setting is "Allow".

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

### -FederationPassiveAddress
Specifies the relative address for the federation passive virtual directory.
By default, /adfs/ls/ address is configured by the AD FS 2.0 Federation Server Configuration Wizard.
If you need to change this value, change this value only after you modify the Internet Information Services (IIS) virtual directory on all federation servers in the Federation Service.

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

If you use this parameter to modify the HTTP port number you also need to manually reset ACLs on the HTTP endpoint URL used by the Federation service.
For more information, see Example 2 below.

By default, the federation server proxy service is configured to use TCP port 80 for HTTP traffic for communication with the federation server.
To configure alternate ports, such as port 81 for HTTP, see the topic "Configuring an Alternate TCP/IP Port for Proxy Operations" in the AD FS Deployment Guide.

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

By default, the federation server proxy service is configured to use TCP port 443 for HTTPS traffic for communication with the federation server.
To configure alternate ports, such as TCP port 444 for HTTPS, see the topic "Configuring an Alternate TCP/IP Port for Proxy Operations" in the AD FS Deployment Guide.

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

### -LogLevel
Specifies the level of logging detail.
The list defines which types of events are logged.

Possible values are Errors, Warnings, Information, SuccessAudits, and FailureAudits.

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

### -MonitoringInterval
Specifies how often the Federation Service will monitor the federation metadata of relying parties and claims providers (in minutes) that are enabled for federation metadata monitoring.

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
Specifies the TCP port for the server.

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
Used to enable support for NTLM-based authentication in situations where the active federation server proxy does not support Negotiate method of authentication.
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
Passes the newly extended AD FS configuration object to the pipeline.
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

### -PreventTokenReplays
Specifies whether the Federation Service is configured to prevent the replay of security tokens.

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

### -ProxyTrustTokenLifetime
Sets the valid token lifetime for proxy trust tokens (in minutes).
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
Specifies the cache duration for token replay detection (in minutes).
This value determines the lifetime in the replay cache for tokens.
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
Specifies the duration for which the SAML messages that the Federation Service sends should be considered valid (in minutes).

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

### -SignSamlAuthnRequests
Indicates whether the Federation Service will sign SAML protocol authentication requests to claims providers.

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
Specifies whether the Federation Service indicates in its federation metadata that it requires signed SAML protocol authentication requests.

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
Specifies the duration of the single sign-on (SSO) experience for Web browser clients (in minutes).

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-ADFSConfiguration](./Get-ADFSConfiguration.md)

