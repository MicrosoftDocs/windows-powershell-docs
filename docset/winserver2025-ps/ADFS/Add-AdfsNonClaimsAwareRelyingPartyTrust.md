---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/add-adfsnonclaimsawarerelyingpartytrust?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-AdfsNonClaimsAwareRelyingPartyTrust
---

# Add-AdfsNonClaimsAwareRelyingPartyTrust

## SYNOPSIS
Adds a relying party trust that represents a non-claims-aware web application or service to the Federation Service.

## SYNTAX

```
Add-AdfsNonClaimsAwareRelyingPartyTrust [-Name] <String> [-Identifier] <String[]>
 [-AlwaysRequireAuthentication] [-Enabled <Boolean>] [-IssuanceAuthorizationRules <String>]
 [-IssuanceAuthorizationRulesFile <String>] [-Notes <String>] [-PassThru]
 [-AdditionalAuthenticationRules <String>] [-AdditionalAuthenticationRulesFile <String>]
 [-AccessControlPolicyName <String>] [-AccessControlPolicyParameters <Object>] [-ClaimsProviderName <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AdfsNonClaimsAwareRelyingPartyTrust** cmdlet creates a relying party trust for web applications or services that do not rely directly on Active Directory Federation Services (AD FS) to issue tokens, but instead rely on a third party that accesses such tokens and transforms them into what applications understand.
A non-claims-aware relying party trust is useful for defining authentication and authorization policies for web applications and services that do not rely on AD FS tokens.
The Web Application Proxy requests such tokens for pre-authentication to web applications or services that have corresponding non-claims-aware relying party trusts for requests that come from outside the network through the proxy.

## EXAMPLES

### Example 1: Add a non-claims-aware relying party trust for an application
```
PS C:\> Add-AdfsNonClaimsAwareRelyingPartyTrust -Name "ExpenseReport" -Identifier "https://contosoexpense/" -IssuanceAuthorizationRules "=>issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");"
```

This command adds a non-claims-aware relying party trust for the application named ExpenseReport and allows all authenticated users to access this application through the Web Application Proxy.

### Example 2: Add a non-claims-aware relying party trust that restricts access to an application
```
PS C:\> Add-AdfsNonClaimsAwareRelyingPartyTrust -Name "ExpenseReport" -Identifier "https://contosoexpense/" -IssuanceAuthorizationRules "c:[type=="http://schemas.microsoft.com/2012/01/devicecontext/claims/isregistereduser"]=>issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");"
```

This command adds a non-claims-aware relying party trust for the application named ExpenseReport and restricts access to this application, through the Web Application Proxy, to only users from their workplace-joined devices.

## PARAMETERS

### -AccessControlPolicyName
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
Specifies rules for additional authentication on the relying party.
For more information about the claims language for rules, see [Understanding Claim Rule Language in AD FS 2.0 & Higher](https://social.technet.microsoft.com/wiki/contents/articles/4792.understanding-claim-rule-language-in-ad-fs-2-0-higher.aspx) on TechNet.

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

### -AdditionalAuthenticationRulesFile
Specifies the file that contains all the rules for additional authentication for the relying party.

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

### -AlwaysRequireAuthentication
Indicates that access requires authentication, even if this relying party has previously authenticated credentials for access.
Specify this parameter to require users to always supply credentials to access sensitive resources.

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

### -ClaimsProviderName
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

### -Enabled
Indicates whether to enable this relying party trust.
Specify a value of $True for this parameter to allow authentication and authorization to the relying party.

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

### -Identifier
Specifies an array of unique identifiers for the non-claims-aware relying party trust.
No other trust can use an identifier from this list.
As common practice, you can use Uniform Resource Identifiers (URIs) as unique identifiers for a relying party trust, or you can use any string.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IssuanceAuthorizationRules
Specifies the authorization rules for issuing claims to the relying party.

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
Specifies the file that contains the authorization rules for issuing claims to the relying party.

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

### -Name
Specifies a name.
The cmdlet adds the Web Application Proxy relying party trust that has the display name that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Notes
Specifies notes for the relying party trust.
Use this parameter to store information such as owners and contacts when you manage a large number of applications.

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

## NOTES

## RELATED LINKS

[Disable-AdfsNonClaimsAwareRelyingPartyTrust](./Disable-AdfsNonClaimsAwareRelyingPartyTrust.md)

[Enable-AdfsNonClaimsAwareRelyingPartyTrust](./Enable-AdfsNonClaimsAwareRelyingPartyTrust.md)

[Get-AdfsNonClaimsAwareRelyingPartyTrust](./Get-AdfsNonClaimsAwareRelyingPartyTrust.md)

[Remove-AdfsNonClaimsAwareRelyingPartyTrust](./Remove-AdfsNonClaimsAwareRelyingPartyTrust.md)

[Set-AdfsNonClaimsAwareRelyingPartyTrust](./Set-AdfsNonClaimsAwareRelyingPartyTrust.md)

