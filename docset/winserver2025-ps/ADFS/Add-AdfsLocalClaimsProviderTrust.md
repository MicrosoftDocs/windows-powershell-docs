---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/add-adfslocalclaimsprovidertrust?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-AdfsLocalClaimsProviderTrust
---

# Add-AdfsLocalClaimsProviderTrust

## SYNOPSIS
Creates a local claims provider trust.

## SYNTAX

```
Add-AdfsLocalClaimsProviderTrust -Name <String> -Identifier <String> [-AcceptanceTransformRules <String>]
 [-AcceptanceTransformRulesFile <String>] [-Enabled <Boolean>] [-Notes <String>]
 [-OrganizationalAccountSuffix <String[]>] [-Force] [-Type <String>] [-PassThru] [-WhatIf] [-Confirm]
 -LdapServerConnection <LdapServerConnection[]> -UserObjectClass <String> -UserContainer <String>
 -AnchorClaimLdapAttribute <String> -AnchorClaimType <String>
 [-LdapAuthenticationMethod <LdapAuthenticationMethod>]
 [-LdapAttributeToClaimMapping <LdapAttributeToClaimMapping[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AdfsLocalClaimsProviderTrust** cmdlet creates a local claims provider trust.
This trust is based on a Lightweight Directory Access Protocol (LDAP) v3 compliant directory other than the Active Directory domain of which the Active Directory Federation Services (AD FS) server is a member.
This includes other, untrusted, Active Directory forests or domains, Active Directory Lightweight Directory Services directories, and non-Active Directory LDAP directories.

## EXAMPLES

### Example 1: Create an LDAP local claims provider trust
```
PS C:\> $Credential = Get-Credential
PS C:\ > $LdapConn = New-AdfsLdapServerConnection -HostName "DomainContoller03.contoso.com" -Port 389 -SslMode None -AuthenticationMethod Basic -Credential $Credential
PS C:\ > $DisplayName = New-AdfsLdapAttributeToClaimMapping -LdapAttribute "displayName" -ClaimType "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/displayname"
PS C:\> Add-AdfsLocalClaimsProviderTrust -Name "testldap" -Identifier "urn:testldap" -Type ldap -LdapServerConnection $LdapConn -UserObjectClass user -UserContainer "CN=Users,DC=<sub_domain_name>,DC=<domain_name>,DC=com" -LdapAuthenticationMethod Basic -AnchorClaimLdapAttribute userPrincipalName -AnchorClaimType "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/upn" -AcceptanceTransformRules "c:[] => issue(claim=c);" -Enabled $True -OrganizationalAccountSuffix "TSQA.contoso.com" - LdapAttributeToClaimMapping $DisplayName
```

The first command prompts you for a user name and password by using the **Get-Credential** cmdlet.
The command stores the results in the $Credential variable.

The second command creates an LDAP connection by using the **New-AdfsLdapServerConnection** cmdlet.
DomainContoller03.contoso.com is the fully qualified domain name of a domain controller in the other forest.
The command stores the result in the $LdapConn variable.

The third command creates a mapping of an LDAP directory attribute to a claim type by using the **New-AdfsLdapAttributeToClaimMapping** cmdlet.

The final command creates an LDAP claims provider trust to authenticate users in another, untrusted Active Directory forest.

## PARAMETERS

### -AcceptanceTransformRules
Specifies the set of claim rules to configure on the local claims provider trust.
These rules determine the information that is accepted from the partner represented by the local claims provider trust.

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

### -AcceptanceTransformRulesFile
Specifies the full path of a file that contains the set of claim rules to configure on the local claims provider trust.

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

### -AnchorClaimLdapAttribute
Specifies the LDAP attribute to which the user name that the user enters isl be matched to find the correct user account in the LDAP directory.

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

### -AnchorClaimType
Specifies the claim type of the anchor claim in AD FS.

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

### -Enabled
Indicates whether the trust is enabled.

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

### -Identifier
Specifies the ID, as a URI, of the claims provider trust.

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

### -LdapAttributeToClaimMapping
Specifies a mapping of LDAP directory attributes to claim types.
Each mapping causes an AD FS claim with the corresponding claim type and LDAP attribute value to be available for AD FS processing rules.
To obtain a mapping, use the **New-AdfsLdapAttributeToClaimMapping** cmdlet.

```yaml
Type: LdapAttributeToClaimMapping[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LdapAuthenticationMethod
Specifies the authentication method the local claims provider trust uses.
In Windows Server 2016, the only supported method is Basic (username/password).

```yaml
Type: LdapAuthenticationMethod
Parameter Sets: (All)
Aliases:
Accepted values: Basic, Kerberos, Negotiate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LdapServerConnection
Specifies an array of LDAP server connections that the claims provider trust uses.
To obtain an **LdapServerConnection** object, use the **New-AdfsLdapServerConnection** cmdlet.

```yaml
Type: LdapServerConnection[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a name for the local claims provider trust.

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

### -Notes
Specifies notes.

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

### -OrganizationalAccountSuffix
Specifies an array of organizational account suffixes that administrator can configure for the claims provider trust for a Home Realm Discovery (HRD) scenario.

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

### -Type
Specifies the type of the claims provider trust.
The acceptable values for this parameter are: ActiveDirectory and LDAP.

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

### -UserContainer
Specifies a user container.

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

### -UserObjectClass
Specifies a user object class.

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

[Disable-AdfsLocalClaimsProviderTrust](./Disable-AdfsLocalClaimsProviderTrust.md)

[Enable-AdfsLocalClaimsProviderTrust](./Enable-AdfsLocalClaimsProviderTrust.md)

[Get-AdfsLocalClaimsProviderTrust](./Get-AdfsLocalClaimsProviderTrust.md)

[New-AdfsLdapAttributeToClaimMapping](./New-AdfsLdapAttributeToClaimMapping.md)

[Remove-AdfsLocalClaimsProviderTrust](./Remove-AdfsLocalClaimsProviderTrust.md)

[Set-AdfsLocalClaimsProviderTrust](./Set-AdfsLocalClaimsProviderTrust.md)

