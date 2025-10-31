---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfswebapplicationproxyrelyingpartytrust?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsWebApplicationProxyRelyingPartyTrust
---

# Set-AdfsWebApplicationProxyRelyingPartyTrust

## SYNOPSIS
Modifies properties of the relying party trust object for the Web Application Proxy.

## SYNTAX

```
Set-AdfsWebApplicationProxyRelyingPartyTrust [-AlwaysRequireAuthentication <Boolean>] [-Identifier <String[]>]
 [-AccessControlPolicyName <String>] [-AccessControlPolicyParameters <Object>]
 [-IssuanceAuthorizationRules <String>] [-IssuanceAuthorizationRulesFile <String>]
 [-IssuanceTransformRules <String>] [-IssuanceTransformRulesFile <String>]
 [-AdditionalAuthenticationRules <String>] [-AdditionalAuthenticationRulesFile <String>] [-Name <String>]
 [-NotBeforeSkew <Int32>] [-Notes <String>] [-PassThru] [-TokenLifetime <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsWebApplicationProxyRelyingPartyTrust** cmdlet modifies properties of the relying party trust object for Web Application Proxy.
You can modify authentication and authorization policies that control all external access through the proxy.

## EXAMPLES

### Example 1: Specify authorization rules by using a file
```
PS C:\> Set-AdfsWebApplicationProxyRelyingPartyTrust -IssuanceAuthorizationRulesFile "C:\Rules\RulesFile07"
```

This command specifies authorization rules for the Web Application Proxy relying party trust, based on a file that contains the rules.

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
Specifies access control policy parameters.

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
Specifies rules for additional authentication on the proxy.
For more information about the claim language for rules, see [Understanding Claim Rule Language in AD FS 2.0 & Higher](https://social.technet.microsoft.com/wiki/contents/articles/4792.understanding-claim-rule-language-in-ad-fs-2-0-higher.aspx) on TechNet.

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
Specifies a file that contains rules for additional authentication for this relying party.

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
Indicates whether access requires authentication, even if this relying party has previously authenticated credentials for access.
Specify a value of $True to require users to always supply credentials to access sensitive resources.

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
Specifies an array of unique identifiers.
The proxy uses the identifiers that you specify to specify its corresponding relying party trust when it initiates sign-in requests to obtain tokens for itself.
No other trust can use an identifier from this list.
As common practice, you can use Uniform Resource Identifiers (URIs) as unique identifiers for a relying party trust, or you can use any string.

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

### -IssuanceAuthorizationRules
Specifies the issuance authorization rules for issuing claims to this relying party.
Issuance authorization rules control access to applications that are enabled for pre-authentication through Active Directory Federation Services (AD FS), and then accessed through the proxy.
By default, all authenticated users can access applications.

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
Specifies a file that contains the issuance authorization rules for issuing claims to this relying party.

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
Specifies the issuance transform rules for issuing claims to this relying party.
You should not, typically, modify the value of this setting.

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
Specifies a file that contains the issuance transform rules for issuing claims to this relying party.

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
The cmdlet modifies the Web Application Proxy relying party trust that has the friendly name that you specify.

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

### -NotBeforeSkew
Specifies the skew, as an integer, for the time stamp that marks the beginning of the validity period.
The higher this number is, the farther back in time the validity period begins with respect to the time that the claims are issued for the relying party.
By default, this value is 0.
Specify a positive value if validation fails on the Web Application Proxy relying party because the validity period has not yet begun.

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

### -Notes
Specifies notes.
The cmdlet stores the notes that you specify for the Web Application Proxy relying party trust.

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

### -TokenLifetime
Specifies the duration, in minutes, for which the claims that are issued to the relying party are valid.

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

[Add-AdfsWebApplicationProxyRelyingPartyTrust](./Add-AdfsWebApplicationProxyRelyingPartyTrust.md)

[Disable-AdfsWebApplicationProxyRelyingPartyTrust](./Disable-AdfsWebApplicationProxyRelyingPartyTrust.md)

[Enable-AdfsWebApplicationProxyRelyingPartyTrust](./Enable-AdfsWebApplicationProxyRelyingPartyTrust.md)

[Get-AdfsWebApplicationProxyRelyingPartyTrust](./Get-AdfsWebApplicationProxyRelyingPartyTrust.md)

[Remove-AdfsWebApplicationProxyRelyingPartyTrust](./Remove-AdfsWebApplicationProxyRelyingPartyTrust.md)

