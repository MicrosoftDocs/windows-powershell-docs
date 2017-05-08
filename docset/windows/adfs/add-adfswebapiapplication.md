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
title: Add-AdfsWebApiApplication
ms.assetid: C55B0698-D72C-46CC-B7AB-C86842F9D692
---

# Add-AdfsWebApiApplication

## SYNOPSIS
Adds a Web API application role to an application in AD FS.

## SYNTAX

### ApplicationGroupIdentifier (Default)
```
Add-AdfsWebApiApplication [-ApplicationGroupIdentifier] <String> -Name <String> -Identifier <String[]>
 [-AllowedAuthenticationClassReferences <String[]>] [-ClaimsProviderName <String[]>]
 [-IssuanceAuthorizationRules <String>] [-IssuanceAuthorizationRulesFile <String>]
 [-DelegationAuthorizationRules <String>] [-DelegationAuthorizationRulesFile <String>]
 [-ImpersonationAuthorizationRules <String>] [-ImpersonationAuthorizationRulesFile <String>]
 [-IssuanceTransformRules <String>] [-IssuanceTransformRulesFile <String>]
 [-AdditionalAuthenticationRules <String>] [-AdditionalAuthenticationRulesFile <String>]
 [-AccessControlPolicyName <String>] [-AccessControlPolicyParameters <Object>] [-NotBeforeSkew <Int32>]
 [-Description <String>] [-TokenLifetime <Int32>] [-AlwaysRequireAuthentication]
 [-AllowedClientTypes <AllowedClientTypes>] [-IssueOAuthRefreshTokensTo <RefreshTokenIssuanceDeviceTypes>]
 [-RefreshTokenProtectionEnabled <Boolean>] [-RequestMFAFromClaimsProviders] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ApplicationGroupObject
```
Add-AdfsWebApiApplication [-ApplicationGroup] <ApplicationGroup> -Name <String> -Identifier <String[]>
 [-AllowedAuthenticationClassReferences <String[]>] [-ClaimsProviderName <String[]>]
 [-IssuanceAuthorizationRules <String>] [-IssuanceAuthorizationRulesFile <String>]
 [-DelegationAuthorizationRules <String>] [-DelegationAuthorizationRulesFile <String>]
 [-ImpersonationAuthorizationRules <String>] [-ImpersonationAuthorizationRulesFile <String>]
 [-IssuanceTransformRules <String>] [-IssuanceTransformRulesFile <String>]
 [-AdditionalAuthenticationRules <String>] [-AdditionalAuthenticationRulesFile <String>]
 [-AccessControlPolicyName <String>] [-AccessControlPolicyParameters <Object>] [-NotBeforeSkew <Int32>]
 [-Description <String>] [-TokenLifetime <Int32>] [-AlwaysRequireAuthentication]
 [-AllowedClientTypes <AllowedClientTypes>] [-IssueOAuthRefreshTokensTo <RefreshTokenIssuanceDeviceTypes>]
 [-RefreshTokenProtectionEnabled <Boolean>] [-RequestMFAFromClaimsProviders] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-AdfsWebApiApplication** cmdlet adds a Web API application role to an application in Active Directory Federation Services (AD FS).

## EXAMPLES


## PARAMETERS

### -AccessControlPolicyName
Specifies the name of an access control policy.

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

### -AccessControlPolicyParameters
Specifies the parameters of an access control policy.

```yaml
Type: Object
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AdditionalAuthenticationRules
Specifies additional authentication rules.

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

### -AdditionalAuthenticationRulesFile
Specifies a file that contains all the rules for additional authentication for this relying party.

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

### -AllowedAuthenticationClassReferences
Specifies an array of allow authentication class references.

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

### -AllowedClientTypes
Specifies allowed client types.
The acceptable values for this parameter are:

- None 
- Public 
- Confidential

```yaml
Type: AllowedClientTypes
Parameter Sets: (All)
Aliases: 
Accepted values: None, Public, Confidential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AlwaysRequireAuthentication
Indicates that this Web API application role always requires authentication, even if it previously authenticated credentials for access.
Specify this parameter to require users to always supply credentials to access sensitive resources.

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

### -ApplicationGroup
Specifies an application group.

```yaml
Type: ApplicationGroup
Parameter Sets: ApplicationGroupObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ApplicationGroupIdentifier
Specifies the ID of an application group.

```yaml
Type: String
Parameter Sets: ApplicationGroupIdentifier
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ClaimsProviderName
Specifies an array of claims provider names that you can configure for a relying party trust for Home Realm Discovery (HRD) scenario.

If claims provider names are specified for a relying party, the home realm discovery page shows only those claims providers for this relying party.
If only one claims provider name is specified, home realm discovery page is not shown.
The user is redirected to this claims provider for authentication.

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

### -DelegationAuthorizationRules
Specifies delegation authorization rules.

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

### -DelegationAuthorizationRulesFile
Specifies a file that contains all the rules for delegation authentication for this relying party.

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

### -Description
Specifies a description.

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

### -Identifier
Specifies an array of identifiers.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ImpersonationAuthorizationRules
Specifies the impersonation authorization rules.

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

### -ImpersonationAuthorizationRulesFile
Specifies a file that contains all the rules for impersonation authentication for this relying party.

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

### -IssuanceAuthorizationRules
Specifies the issuance authorization rules.

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

### -IssuanceAuthorizationRulesFile
Specifies a file that contains all the rules for issuance authentication for this relying party.

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

### -IssuanceTransformRules
Specifies the issuance transform rules.

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

### -IssuanceTransformRulesFile
Specifies a file that contains all the rules for issuance transform for this relying party.

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

### -IssueOAuthRefreshTokensTo
Specifies the refresh token issuance device types.
The acceptable values for this parameter are:

- NoDevice 
- WorkplaceJoinedDevices 
- AllDevices

```yaml
Type: RefreshTokenIssuanceDeviceTypes
Parameter Sets: (All)
Aliases: 
Accepted values: NoDevice, WorkplaceJoinedDevices, AllDevices

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

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotBeforeSkew
Specifies the not before skew value.

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

### -RefreshTokenProtectionEnabled
Indicates whether refresh token protection is enabled.

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

### -RequestMFAFromClaimsProviders
Indicates that the request MFA from claims providers option is used.

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

### -TokenLifetime
Specifies the token lifetime.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS
**Microsoft.IdentityServer.Management.Resources.WebApiApplication**

	AccessControlPolicyName               string
	AccessControlPolicyParameters         System.Object
	AdditionalAuthenticationRules         string
	AllowedAuthenticationClassReferences  string[]
	AllowedClientTypes                    Microsoft.IdentityServer.Protocols.PolicyStore.AllowedClientTypes
	AlwaysRequireAuthentication           bool
	ApplicationGroupId                    string
	ApplicationGroupIdentifier            string
	ClaimsProviderName                    string[]
	DelegationAuthorizationRules          string
	Description                           string
	Enabled                               bool
	Identifier                            System.Collections.ObjectModel.ReadOnlyCollection[string]
	ImpersonationAuthorizationRules       string
	IssuanceAuthorizationRules            string
	IssuanceTransformRules                string
	IssueOAuthRefreshTokensTo             Microsoft.IdentityServer.Protocols.PolicyStore.RefreshTokenIssuanceDeviceTypes
	Name                                  string
	NotBeforeSkew                         int
	PublishedThroughProxy                 bool
	RefreshTokenProtectionEnabled         bool
	RequestMFAFromClaimsProviders         bool
	ResultantPolicy                       Microsoft.IdentityServer.PolicyModel.Configuration.PolicyTemplate.PolicyMetadata
	TokenLifetime                         int

**Microsoft.IdentityServer.Protocols.PolicyStore.AllowedClientTypes**
	
	AllowedClientTypes
	{
	  None = 0,
	  Public = 2,
	  Confidential=4,
	}


**Microsoft.IdentityServer.Protocols.PolicyStore.RefreshTokenIssuanceDeviceTypes**
	
	RefreshTokenIssuanceDeviceTypes
	{
	  NoDevice = 0,
	  WorkplaceJoinedDevices = 1,
	  AllDevices = 2
	}
	

**Microsoft.IdentityServer.PolicyModel.Configuration.PolicyTemplate.PolicyMetadata**

	IsParameterized  bool
	Summary          string
	Serialized       string

## NOTES

## RELATED LINKS

[Get-AdfsWebApiApplication](./Get-AdfsWebApiApplication.md)

[Remove-AdfsWebApiApplication](./Remove-AdfsWebApiApplication.md)

[Set-AdfsWebApiApplication](./Set-AdfsWebApiApplication.md)

