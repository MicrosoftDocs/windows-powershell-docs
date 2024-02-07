---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/get-adfswebapplicationproxyrelyingpartytrust?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AdfsWebApplicationProxyRelyingPartyTrust
---

# Get-AdfsWebApplicationProxyRelyingPartyTrust

## SYNOPSIS
Gets the relying party trust object for the Web Application Proxy.

## SYNTAX

```
Get-AdfsWebApplicationProxyRelyingPartyTrust [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsWebApplicationProxyRelyingPartyTrust** cmdlet gets the Web Application Proxy relying party trust object for the proxy.

The Web Application Proxy relying party trust is useful to manage global network access from outside the corporate network.
By setting authentication and authorization policies, an administrator can restrict access to internal web applications and services that are published through the Web Application Proxy.

## EXAMPLES

### Example 1: Get the relying party trust object
```
PS C:\> Get-AdfsWebApplicationProxyRelyingPartyTrust

AlwaysRequireAuthentication   : False
Enabled                       : True
Identifier                    : {urn:AppProxy:com}
IssuanceAuthorizationRules    : @RuleTemplate="AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value="true");
IssuanceTransformRules        : @RuleTemplate="PassThroughClaims"
@RuleName="Pass Through Application Identifier"
c:[Type == "http://schemas.contoso.com/2012/01/requestcontext/claims/relyingpartytrustid"] => issue(claim = c);
@RuleTemplate="PassThroughClaims"
@RuleName="Pass Through Device Registration Identifier"
c:[Type == "http://schemas.contoso.com/2012/01/devicecontext/claims/registrationid"] => issue(claim = c);
@RuleTemplate="PassThroughClaims"
@RuleName="Pass Through UPN"
c:[Type == "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/upn"] => issue(claim = c);
@RuleTemplate="PassThroughClaims"
@RuleName="Pass Through Activity ID"
c:[Type == "http://schemas.contoso.com/2012/01/requestcontext/claims/client-request-id"] => issue(claim = c);

AdditionalAuthenticationRules :
Name                          : urn:AppProxy:com
NotBeforeSkew                 : 0
Notes                         :
RelyingPartyType              : WebApplicationProxy
TokenLifetime                 : 0
```

This command gets the Web Application Proxy relying party trust object.
The command displays authentication and authorization rules added previously.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AdfsWebApplicationProxyRelyingPartyTrust](./Add-AdfsWebApplicationProxyRelyingPartyTrust.md)

[Disable-AdfsWebApplicationProxyRelyingPartyTrust](./Disable-AdfsWebApplicationProxyRelyingPartyTrust.md)

[Enable-AdfsWebApplicationProxyRelyingPartyTrust](./Enable-AdfsWebApplicationProxyRelyingPartyTrust.md)

[Remove-AdfsWebApplicationProxyRelyingPartyTrust](./Remove-AdfsWebApplicationProxyRelyingPartyTrust.md)

[Set-AdfsWebApplicationProxyRelyingPartyTrust](./Set-AdfsWebApplicationProxyRelyingPartyTrust.md)

