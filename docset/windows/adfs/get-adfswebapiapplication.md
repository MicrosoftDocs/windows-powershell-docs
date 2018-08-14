---
author: coreyp-at-msft
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: ADFS
ms.assetid: CC8998A0-12E0-4CBA-A56B-FBFC5F399AA2
ms.author: coreyp
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-AdfsWebApiApplication
---

# Get-AdfsWebApiApplication

## SYNOPSIS
Gets Web API application roles in AD FS.

## SYNTAX

### Identifier (Default)
```
Get-AdfsWebApiApplication [[-Identifier] <String[]>] [<CommonParameters>]
```

### Name
```
Get-AdfsWebApiApplication [-Name] <String[]> [<CommonParameters>]
```

### PrefixIdentifier
```
Get-AdfsWebApiApplication [-PrefixIdentifier] <String> [<CommonParameters>]
```

### ApplicationObject
```
Get-AdfsWebApiApplication [-Application] <WebApiApplication> [<CommonParameters>]
```

### ApplicationGroupIdentifier
```
Get-AdfsWebApiApplication [-ApplicationGroupIdentifier] <String> [<CommonParameters>]
```

### ApplicationGroupObject
```
Get-AdfsWebApiApplication [-ApplicationGroup] <ApplicationGroup> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsWebApiApplication** cmdlet gets Web API application roles in Active Directory Federation Services (AD FS).

## EXAMPLES

## PARAMETERS

### -Application
Specifies a Web API application to get.

```yaml
Type: WebApiApplication
Parameter Sets: ApplicationObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ApplicationGroup
Specifies an application group for which to get Web API applications.

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
Specifies the ID of an application group for which to get Web API applications.

```yaml
Type: String
Parameter Sets: ApplicationGroupIdentifier
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Identifier
Specifies an ID of a Web API application to get.

```yaml
Type: String[]
Parameter Sets: Identifier
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
Specifies an array of names of Web API applications to get.

```yaml
Type: String[]
Parameter Sets: Name
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PrefixIdentifier
Specifies the prefix identifier of Web API applications to get.

```yaml
Type: String
Parameter Sets: PrefixIdentifier
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]
Microsoft.IdentityServer.Management.Resources.WebApiApplication
System.String
Microsoft.IdentityServer.Management.Resources.ApplicationGroup

## OUTPUTS

### Microsoft.IdentityServer.Management.Resources.WebApiApplication
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

### Microsoft.IdentityServer.Protocols.PolicyStore.AllowedClientTypes
	
	AllowedClientTypes
	{
	  None = 0,
	  Public = 2,
	  Confidential=4,
	}

### Microsoft.IdentityServer.Protocols.PolicyStore.RefreshTokenIssuanceDeviceTypes
	
	RefreshTokenIssuanceDeviceTypes
	{
	  NoDevice = 0,
	  WorkplaceJoinedDevices = 1,
	  AllDevices = 2
	}
	

### Microsoft.IdentityServer.PolicyModel.Configuration.PolicyTemplate.PolicyMetadata
	IsParameterized  bool
	Summary          string
	Serialized       string

## NOTES
Microsoft.IdentityServer.Management.Resources.WebApiApplication inherits from Microsoft.IdentityServer.Management.Resources.ClientApplication object and implements the Microsoft.IdentityServer.Management.Resources.IApplication interface.

		Microsoft.IdentityServer.Management.Resources.ClientApplication
		
		ApplicationGroupIdentifier                        string
		Description                                       string
		Enabled                                           bool
		Identifier                                        string
		Name                                              string
		RedirectUri                                       string[]
		
		Microsoft.IdentityServer.Management.Resources.IApplication
		
		ApplicationGroupIdentifier                        string
		Enabled                                           bool
		Name                                              string

## RELATED LINKS

[Add-AdfsWebApiApplication](./Add-AdfsWebApiApplication.md)

[Remove-AdfsWebApiApplication](./Remove-AdfsWebApiApplication.md)

[Set-AdfsWebApiApplication](./Set-AdfsWebApiApplication.md)

