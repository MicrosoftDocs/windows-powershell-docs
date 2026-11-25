---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/add-adfswebapplicationproxyrelyingpartytrust?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-AdfsWebApplicationProxyRelyingPartyTrust
---

# Add-AdfsWebApplicationProxyRelyingPartyTrust

## SYNOPSIS
Adds a relying party trust for the Web Application Proxy.

## SYNTAX

```
Add-AdfsWebApplicationProxyRelyingPartyTrust [-Name] <String> [-Identifier] <String[]>
 [-AlwaysRequireAuthentication] [-Enabled <Boolean>] [-AccessControlPolicyName <String>]
 [-AccessControlPolicyParameters <Object>] [-AdditionalAuthenticationRules <String>]
 [-AdditionalAuthenticationRulesFile <String>] [-NotBeforeSkew <Int32>] [-Notes <String>] [-PassThru]
 [-TokenLifetime <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AdfsWebApplicationProxyRelyingPartyTrust** cmdlet adds a relying party trust for Web Application Proxy.
Authentication and authorization policies for access to internal web applications through the proxy require Web Application Proxy relying party trust.
By default, when you deploy Web Application Proxy, a relying party trust exists.

The Web Application Proxy relying party trust is useful to manage global network access from outside the corporate network.
By setting authentication and authorization policies, an administrator can restrict access to internal web applications and services that are published through the Web Application Proxy.

## EXAMPLES

### Example 1: Add a relying party trust
```
PS C:\> Add-AdfsWebApplicationProxyRelyingPartyTrust
```

This command adds the Web Application Proxy relying party trust.
When you first deploy the Web Application Proxy role service, the trust exists by default.
Use this example only if you deleted the Web Application Proxy relying party trust.

## PARAMETERS

### -AccessControlPolicyName
Specifies the name of the access control policy.

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
Specifies the parameters of the access control policy.

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
Indicates that the proxy requires authentication for access, even if the proxy has previously authenticated credentials for access.
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

### -Enabled
Indicates whether to enable this relying party trust.
Specify a value of $True for this parameter to allow authentication and authorization to the proxy.

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
As common practice, you can use Uniform Resource Identifiers (URIs) as unique identifiers for a relying party trust, or use any string.

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

### -Name
Specifies a name.
The cmdlet adds the Web Application Proxy relying party trust that has the friendly name that you specify.

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

### -NotBeforeSkew
Specifies the skew, as an integer, for the time stamp that marks the beginning of the validity period.
The higher this number is, the further back in time the validity period begins with respect to the time that the claims are issued for the relying party.
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

[Disable-AdfsWebApplicationProxyRelyingPartyTrust](./Disable-AdfsWebApplicationProxyRelyingPartyTrust.md)

[Enable-AdfsWebApplicationProxyRelyingPartyTrust](./Enable-AdfsWebApplicationProxyRelyingPartyTrust.md)

[Get-AdfsWebApplicationProxyRelyingPartyTrust](./Get-AdfsWebApplicationProxyRelyingPartyTrust.md)

[Remove-AdfsWebApplicationProxyRelyingPartyTrust](./Remove-AdfsWebApplicationProxyRelyingPartyTrust.md)

[Set-AdfsWebApplicationProxyRelyingPartyTrust](./Set-AdfsWebApplicationProxyRelyingPartyTrust.md)

