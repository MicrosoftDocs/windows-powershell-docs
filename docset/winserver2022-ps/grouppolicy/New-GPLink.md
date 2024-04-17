---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
Module Name: GroupPolicy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/grouppolicy/new-gplink?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-GPLink
---

# New-GPLink

## SYNOPSIS

Links a GPO to a site, domain, or OU.

## SYNTAX

### LinkbyGUID (Default)

```
New-GPLink -Guid <Guid> -Target <String> [-LinkEnabled <EnableLink>] [-Order <Int32>]
 [-Domain <String>] [-Server <String>] [-Enforced <EnforceLink>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### LinkbyName

```
New-GPLink [-Name] <String> -Target <String> [-LinkEnabled <EnableLink>] [-Order <Int32>]
 [-Domain <String>] [-Server <String>] [-Enforced <EnforceLink>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The `New-GPLink` cmdlet links a GPO to a site, domain, or organizational unit (OU). By default,
the link is enabled, which means that the settings of the GPO are applied at the level of the target
Active Directory container according to the rules of inheritance and precedence when Group Policy is
processed.

You can specify the GPO by either its display name or its GUID; or the GPO can be piped into the
cmdlet. You specify the site, domain, or organizational unit (OU) to link to by its Lightweight
Directory Access Protocol (LDAP) distinguished name. You can use other parameters to specify whether
the link is enabled, whether the link is enforced, and the order in which it is applied at the site,
domain, or OU.

## EXAMPLES

### Example 1: Create and link a GPO to a domain

```powershell
New-GPO -Name "MyGPO" | New-GPLink -Target "ou=MyOU,dc=contoso,dc=com" -LinkEnabled Yes
```

```Output
GpoId       : c25daa3e-5d05-43b3-87ca-0a237882fd63 
DisplayName : MyGPO 
Enabled     : True 
Enforced    : False 
Target      : OU=MyOU,DC=contoso,DC=com 
Order       : 1
```

This command creates the GPO named MyGPO in the domain of the user (or, for a startup or shutdown
script, the computer) and links it to the `MyOU` organizational unit in the `contoso.com` domain. If
the domain of the user, or the computer, is different than `contoso.com`, a trust relationship must
exist between the two domains.

Because this command can take a GPO as input, you can insert any command that returns a GPO between
`New-GPO` and `New-GPLink` to configure the GPO. For instance, you can insert `Set-GPPermissions`
commands to set permissions on the GPO, `Set-GPRegistryValue` cmdlet to configure one or more
registry-based policy settings for the GPO, or the `Set-GPPrefRegistryValue` cmdlet to configure
one or more Registry preference items for the GPO.

### Example 2: Link a GPO in the domain of the user

```powershell
New-GPLink -Name "TestGPO" -Target "dc=contoso,dc=com"
```

```Output
GpoId       : d5a3b4e7-e37a-4070-846c-568689eaa838 
DisplayName : TestGPO 
Enabled     : True 
Enforced    : False 
Target      : DC=contoso,DC=com 
Order       : 2
```

This command links the `TestGPO` GPO in the domain of the user (or, for a startup or shutdown
script, the computer) to the `contoso.com` domain. If the domain of the user, or the computer, is
different than `contoso.com`, a trust relationship must exist between the two domains.

### Example 3: Link a GPO to a site and enforce the link

```powershell
New-GPLink -name "TestGPO" -Target "Test-Site" -Enforced Yes 
```

```Output
GpoId       : d5a3b4e7-e37a-4070-846c-568689eaa838 
DisplayName : TestGPO 
Enabled     : True 
Enforced    : True 
Target      : CN=test-site,cn=Sites,CN=Configuration,DC=contoso,DC=com 
Order       : 1
```

This command links the `TestGPO` GPO to the site named `Test-Site` and sets the link to enforced.

## PARAMETERS

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Domain

Specifies the domain for this cmdlet. You must specify the fully qualified domain name (FQDN) of the
domain.

For the `New-GPLink` cmdlet:

- The GPO to link from must exist in this domain.

- The Active Directory container to link to must exist in a domain that has a trust relationship
  with this domain.

To specify a domain to link to, use the *Target* parameter.

If you do not specify the **Domain** parameter, the domain of the user that is running the current
session is used. If the cmdlet is being run from a computer startup or shutdown script, the domain
of the computer is used. For more information, see the Notes section in the full Help.

If you specify a domain that is different from the domain of the user that is running the current
session (or, for a startup or shutdown script, the computer), a trust must exist between that domain
and the domain of the user, or the computer.

You can also refer to **Domain** by its built-in alias, **DomainName**. For more information, see
[about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DomainName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enforced

Specifies whether the GPO link is enforced. You can specify Yes or No. By default, GPO links are not
enforced.

By setting the GPO link to enforced, you ensure the following:

- That the settings of the GPO cannot be blocked (by blocking inheritance) at a lower-level Active
  Directory container.
- That the settings of the GPO always take precedence over conflicting settings in GPOs that are
  linked to lower-level containers.

This option should be used sparingly. Casual use of this option complicates troubleshooting.

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

Specifies the GPO to link by its globally unique identifier (GUID). The GUID uniquely identifies the
GPO in the domain.

You can also refer to the **Guid** parameter by its built-in alias, **Id**. For more information, see
[about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

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

The acceptable values for this parameter are: Yes or No.

By default, Group Policy processing is enabled for all GPO links. You can completely block the
application of a GPO for a specific site, domain, or OU by disabling the GPO link for that site,
domain, or OU. Disabling a GPO link does not disable the GPO itself. If the GPO is linked to other
sites, domains, or OUs, Group Policy continues to process the GPO for each link that is enabled.

```yaml
Type: EnableLink
Parameter Sets: (All)
Aliases: 
Accepted values: Unspecified, No, Yes

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Specifies the GPO to link by its display name.

The display name is not guaranteed to be unique in the domain. If another GPO with the same display
name exists in the domain, an error occurs. You can use the **Guid** parameter to uniquely identify
a GPO.

You can also refer to the **Name** parameter by its built-in alias, **DisplayName**. For more
information, see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: System.String
Parameter Sets: LinkbyName
Aliases: DisplayName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Order

Specifies the link order for the GPO link. You can specify a number that is between one and the
current number of GPO links to the target site, domain, or OU, plus one.

The link order specifies the order of precedence with which GPOs linked to the same Active Directory
container are applied. When Group Policy is processed, GPOs with a higher link order number are
processed before GPOs with a lower link order number. Therefore, when two GPOs contain conflicting
settings, the settings in the GPO with the lower link order number, because it is processed last,
overwrites those of the GPO with the higher link order number. A lower number indicates higher
precedence.

By default, the GPO link is added at the lowest precedence with a link order equal to the number of
GPO links to the container, plus one. Link order is a dynamic value because the value may change as
GPO links are added and deleted from the container. You can change the link order of a GPO link with
the `Set-GPLink` cmdlet.

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

Specifies the name of the domain controller that this cmdlet contacts to complete the operation. You
can specify either the FQDN or the host name.

If you do not specify the name by using the **Server** parameter, the primary domain controller
(PDC) emulator is contacted.

You can also refer to the **Server** parameter by its built-in alias, **DC**. For more information,
see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Target

Specifies the LDAP distinguished name of the site, domain, or OU to which to link the GPO. For
example, for the `MyOU` organizational unit in the `contoso.com` domain, the LDAP distinguished name
is `ou=MyOU,dc=contoso,dc=com`.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.GroupPolicy.Gpo

You can pipe a GPO object to be linked to an Active Directory container.
Collections that contain GPOs from different domains are not supported.

## OUTPUTS

### Microsoft.GroupPolicy.GpoLink

This cmdlet returns an object that represents the link between the GPO and the site, domain, or OU.

## NOTES

* To link a GPO to a site, domain, or OU, you must have Link GPOs permission on that site, domain,
  or OU. By default, only domain administrators and enterprise administrators have this privilege
  for domains and OUs. Enterprise administrators and domain administrators of the forest root domain
  have this privilege for sites.

  You can use the **Domain** parameter to explicitly specify the domain for this cmdlet.

  If you do not explicitly specify the domain, the cmdlet uses a default domain. The default domain
  is the domain that is used to access network resources by the security context under which the
  current session is running. This domain is typically the domain of the user that is running the
  session. For instance, the domain of the user who started the session by opening Windows
  PowerShell from the Program Files menu, or the domain of a user that is specified in a runas
  command. However, computer startup and shutdown scripts run under the context of the LocalSystem
  account. The LocalSystem account is a built-in local account, and it accesses network resources
  under the context of the computer account. Therefore, when this cmdlet is run from a startup or
  shutdown script, the default domain is the domain to which the computer is joined.

## RELATED LINKS

[Remove-GPLink](./Remove-GPLink.md)

[Set-GPLink](./Set-GPLink.md)

[Set-GPPrefRegistryValue](./Set-GPPrefRegistryValue.md)

[Set-GPRegistryValue](./Set-GPRegistryValue.md)

