---
author: Kateyanne
description: 
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
manager: jasgro
Module Name: GroupPolicy
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/grouppolicy/new-gplink?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-GPLink
---

# New-GPLink

## SYNOPSIS
Links a GPO to a site, domain, or organizational unit (OU).

## SYNTAX

### LinkbyGUID (Default)
```
New-GPLink -Guid <Guid> -Target <String> [-LinkEnabled <EnableLink>] [-Order <Int32>] [-Domain <String>]
 [-Server <String>] [-Enforced <EnforceLink>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LinkbyName
```
New-GPLink [-Name] <String> -Target <String> [-LinkEnabled <EnableLink>] [-Order <Int32>] [-Domain <String>]
 [-Server <String>] [-Enforced <EnforceLink>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The New-GPLink cmdlet links a GPO to a site, domain, or OU.
By default, the link is enabled, which means that the settings of the GPO are applied at the level of the target Active Directory container (site, domain, or OU) according to the rules of inheritance and precedence when Group Policy is processed.

You can specify the GPO by either its display name or its GUID; or the GPO can be piped into the cmdlet.
You specify the site, domain, or OU to link to by its LDAP distinguished name.
You can use other parameters to specify whether the link is enabled, whether the link is enforced, and the order in which it is applied at the site, domain, or OU.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\> New-GPO -Name "MyGPO" | New-GPLink -target "ou=MyOU,dc=contoso,dc=com" -LinkEnabled Yes 

GpoId       : c25daa3e-5d05-43b3-87ca-0a237882fd63 
DisplayName : MyGPO 
Enabled     : True 
Enforced    : False 
Target      : OU=MyOU,DC=contoso,DC=com 
Order       : 1
```

Description

-----------

This command creates the "MyGPO" GPO in the domain of the user (or, for a startup or shutdown script, the computer) and links it to the "MyOU" organizational unit in the contoso.com domain.
If the domain of the user (or the computer) is different than contoso.com, a trust relationship must exist between the two domains.

Because New-GPLink can take a GPO as input, you can insert any command that returns a GPO between New-GPO and New-GPLink to configure the GPO.
For example, you can insert Set-GPPermissions commands to set permissions on the GPO, Set-GPRegistryValue commands to configure one or more registry-based policy settings for the GPO, or Set-GPPrefRegistryValue commands to configure one or more Registry preference items for the GPO.

### -------------------------- EXAMPLE 2 --------------------------
```
PS C:\> new-gplink -name testgpo -target "dc=contoso,dc=com" 

GpoId       : d5a3b4e7-e37a-4070-846c-568689eaa838 
DisplayName : TestGPO 
Enabled     : True 
Enforced    : False 
Target      : DC=contoso,DC=com 
Order       : 2
```

Description

-----------

This command links the "TestGPO" GPO in the domain of the user (or, for a startup or shutdown script, the computer) to the contoso.com domain.
If the domain of the user (or the computer) is different than contoso.com, a trust relationship must exist between the two domains.

### -------------------------- EXAMPLE 3 --------------------------
```
PS C:\> new-gplink -name testgpo -target "test-site" -enforced yes 

GpoId       : d5a3b4e7-e37a-4070-846c-568689eaa838 
DisplayName : TestGPO 
Enabled     : True 
Enforced    : True 
Target      : CN=test-site,cn=Sites,CN=Configuration,DC=contoso,DC=com 
Order       : 1
```

Description

-----------

This command links the "TestGPO" GPO to the "test-site" site and sets the link to enforced.

## PARAMETERS

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

### -Domain
Specifies the domain for this cmdlet.
You must specify the fully qualified domain name (FQDN) of the domain (for example: sales.contoso.com).

For the New-GPLink cmdlet:

- The GPO to link from must exist in this domain.

- The Active Directory container to link to must exist in a domain that has a trust relationship with this domain.

Note: To specify a domain to link to, use the Target parameter.

If you do not specify the Domain parameter, the domain of the user that is running the current session is used.
(If the cmdlet is being run from a computer startup or shutdown script, the domain of the computer is used.) For more information, see the Notes section in the full Help.

If you specify a domain that is different from the domain of the user that is running the current session (or, for a startup or shutdown script, the computer), a trust must exist between that domain and the domain of the user (or the computer).

You can also refer to Domain by its built-in alias, "domainname".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DomainName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enforced
Specifies whether the GPO link is enforced.
You can specify Yes or No.
By default, GPO links are not enforced.

By setting the GPO link to enforced, you ensure the following:

- That the settings of the GPO cannot be blocked (by blocking inheritance) at a lower-level Active Directory container.

- That the settings of the GPO always take precedence over conflicting settings in GPOs that are linked to lower-level containers.

This option should be used sparingly.
Casual use of this option complicates troubleshooting.

The following values are permitted for this object type.

```yaml
Type: EnforceLink
Parameter Sets: (All)
Aliases: 
Accepted values: Unspecified, No, Yes

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Guid
Specifies the GPO to link by its globally unique identifier (GUID).
The GUID uniquely identifies the GPO in the domain.

You can also refer to the Guid parameter by its built-in alias, "id".
For more information, see about_Aliases.

```yaml
Type: Guid
Parameter Sets: LinkbyGUID
Aliases: ID

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LinkEnabled
Specifies whether the GPO link is enabled.
You can specify Yes or No.

By default, Group Policy processing is enabled for all GPO links.
You can completely block the application of a GPO for a specific site, domain, or OU by disabling the GPO link for that site, domain, or OU.
Disabling a GPO link does not disable the GPO itself.
If the GPO is linked to other sites, domains, or OUs, Group Policy continues to process the GPO for each link that is enabled.

The following values are permitted for this object type.

```yaml
Type: EnableLink
Parameter Sets: (All)
Aliases: 
Accepted values: Unspecified, No, Yes

Required: False
Position: Named
Default value: Disabled
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the GPO to link by its display name.

The display name is not guaranteed to be unique in the domain.
If another GPO with the same display name exists in the domain, an error occurs.
You can use the Guid parameter to uniquely identify a GPO.

You can also refer to the Name parameter by its built-in alias, "displayname".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: LinkbyName
Aliases: DisplayName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Order
Specifies the link order for the GPO link.
You can specify a number that is between one and the current number of GPO links to the target site, domain, or OU, plus one.

The link order specifies the order of precedence with which GPOs linked to the same Active Directory container are applied.
When Group Policy is processed, GPOs with a higher link order number are processed before GPOs with a lower link order number.
Therefore, when two GPOs contain conflicting settings, the settings in the GPO with the lower link order number, because it is processed last, overwrites those of the GPO with the higher link order number.
A lower number indicates higher precedence.

By default, the GPO link is added at the lowest precedence (with a link order equal to the number of GPO links to the container, plus one).
Link order is a dynamic value because the value may change as GPO links are added and deleted from the container.
You can change the link order of a GPO link with the Set-GPLink cmdlet.

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

### -Server
Specifies the name of the domain controller that this cmdlet contacts to complete the operation.
You can specify either the fully qualified domain name (FQDN) or the host name.
For example:

FQDN: DomainController1.sales.contoso.com

Host Name: DomainController1

If you do not specify the name by using the Server parameter, the PDC emulator is contacted.

You can also refer to the Server parameter by its built-in alias, "dc".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Target
Specifies the LDAP distinguished name of the site, domain, or OU to which to link the GPO.
For example, for the "MyOU" organizational unit in the contoso.com domain, the LDAP distinguished name is "ou=MyOU,dc=contoso,dc=com".

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

### Microsoft.GroupPolicy.Gpo
A GPO to be linked to an Active Directory container.
Collections that contain GPOs from different domains are not supported.

## OUTPUTS

### Microsoft.GroupPolicy.GpoLink
New-GPLink returns an object that represents the link between the GPO and the site, domain, or OU.

## NOTES
* To link a GPO to a site, domain, or OU, you must have Link GPOs permission on that site, domain, or OU. By default, only domain administrators and enterprise administrators have this privilege for domains and OUs. Enterprise administrators and domain administrators of the forest root domain have this privilege for sites.

  You can use the Domain parameter to explicitly specify the domain for this cmdlet.

  If you do not explicitly specify the domain, the cmdlet uses a default domain.
The default domain is the domain that is used to access network resources by the security context under which the current session is running.
This domain is typically the domain of the user that is running the session.
For example, the domain of the user who started the session by opening Windows PowerShell from the Program Files menu, or the domain of a user that is specified in a runas command.
However, computer startup and shutdown scripts run under the context of the LocalSystem account.
The LocalSystem account is a built-in local account, and it accesses network resources under the context of the computer account.
Therefore, when this cmdlet is run from a startup or shutdown script, the default domain is the domain to which the computer is joined.

## RELATED LINKS

[Remove-GPLink](./Remove-GPLink.md)

[Set-GPLink](./Set-GPLink.md)

