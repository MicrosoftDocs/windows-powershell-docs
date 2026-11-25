---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
Module Name: GroupPolicy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/grouppolicy/set-gplink?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-GPLink
---

# Set-GPLink

## SYNOPSIS

Sets the properties of the specified GPO link.

## SYNTAX

### LinkGUID (Default)

```
Set-GPLink -Guid <Guid> -Target <String> [-LinkEnabled <EnableLink>] [-Order <Int32>]
 [-Domain <String>] [-Server <String>] [-Enforced <EnforceLink>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### LinkName

```
Set-GPLink [-Name] <String> -Target <String> [-LinkEnabled <EnableLink>] [-Order <Int32>]
 [-Domain <String>] [-Server <String>] [-Enforced <EnforceLink>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The **Set-GPLink** cmdlet sets the properties of a Group Policy Object (GPO) link.

You can set the following properties:

- Enabled. If the GPO link is enabled, the settings of the GPO are applied when Group Policy is
  processed for the site, domain or OU.

- Enforced.
  If the GPO link is enforced, it cannot be blocked at a lower-level (in the Group Policy
  processing hierarchy) container.

- Order.
  The order specifies the precedence that the settings of the GPO take over conflicting
  settings in other GPOs that are linked, and enabled, to the same site, domain, or OU.

## EXAMPLES

### Example 1: Enable the link between a GPO and OU

```powershell
Set-GPLink -Name TestGPO -Target "ou=MyOU,dc=contoso,dc=com" -LinkEnabled Yes
```

```Output
GpoId       : c25daa3e-5d05-43b3-87ca-0a237882fd63
DisplayName : Test2GPO
Enabled     : True
Enforced    : False
Target      : OU=MyOU,DC=contoso,DC=com
Order       : 1
```

This command enables the link between the GPO named `TestGPO` and the `MyOU` organizational unit
in the `contoso.com` domain. The **Enforced** and **Order** properties are not changed.

### Example 2: Enable the link between a GPO and two domains

```powershell
$params = @{
    Name        = 'TestGPO'
    Domain      = "north.contoso.com"
    Target      = "dc=south,dc=contoso,dc=com"
    LinkEnabled = $true
    Enforced    = $true
    Order       = 1
}
Set-GPLink @params
```

This command enables the link between the GPO named `TestGPO` in the `north.contoso.com` domain and
the `south.contoso.com` domain. The link is set to enforced, so it cannot be blocked at lower-level
containers (for example OUs in the `south.contoso.com` domain). Because the order is set to `1`, the
settings of `TestGPO` is applied with the highest precedence (except for enforced links) when Group
policy is processed for the `south.contoso.com` domain container.

### Example 3: Set the enforced property of a link between a GPO and a test site

```powershell
Set-GPLink -Guid 77c5285d-952e-4559-94ef-a02f5c107799 -Target "Test-Site" -Enforced Yes
```

```Output
GpoId       : 77c5285d-952e-4559-94ef-a02f5c107799
DisplayName : TestGPO
Enabled     : True
Enforced    : True
Target      : CN=test-site,cn=Sites,CN=Configuration,DC=contoso,DC=com
Order       : 1
```

This command sets the enforced property of the link between the GPO that has ID
`77c5285d-952e-4559-94ef-a02f5c107799` and the `Test-Site`. Inheritance cannot be blocked for this
link at containers that are at lower-levels of the Group Policy hierarchy.

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

Specifies the domain for this cmdlet.
You must specify the fully qualified domain name (FQDN) of the domain.

For the **Set-GPLink** cmdlet:

- The GPO that is linked from must exist in this domain.

- The Active Directory container that is linked to must exist in a domain that has a trust
  relationship with this domain.

To specify a domain to link to, use the **Target** parameter.

If you do not specify the **Domain** parameter, the domain of the user that is running the current
session is used. If the cmdlet is being run from a computer startup or shutdown script, the domain
of the computer is used. For more information, see the Notes section in the full Help.

If you specify a domain that is different from the domain of the user that is running the current
session (or, for a startup or shutdown script, the computer), a trust must exist between that domain
and the domain of the user or the computer.

You can also refer to the **Domain** parameter by its built-in alias, **DomainName**. For more
information, see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

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

Specifies the GPO of the link by its globally unique identifier (GUID). The GUID uniquely identifies
the GPO.

You can also refer to the **Guid** parameter by its built-in alias, **Id**.

```yaml
Type: Guid
Parameter Sets: LinkGUID
Aliases: ID, GPOID

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LinkEnabled

Specifies whether the GPO link is enabled. You can specify Yes or No.

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

Specifies the GPO of the link by its display name.

The display name is not guaranteed to be unique in the domain. If another GPO with the same display
name exists in the domain, an error occurs. You can use the **Guid** parameter to uniquely identify
a GPO.

You can also refer to the **Name** parameter by its built-in alias, **DisplayName**.

```yaml
Type: System.String
Parameter Sets: LinkName
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

By default, the GPO link is added at the lowest precedence (with a link order equal to the number of
GPO links to the container, plus one). Link order is a dynamic value because the value may change as
GPO links are added and deleted from the container.

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
can specify either the fully qualified domain name (FQDN) or the host name.

If you do not specify the name by using the **Server** parameter, the primary domain controller
(PDC) emulator is contacted.

You can also refer to the **Server** parameter by its built-in alias, **DC**.

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

Specifies the Lightweight Directory Access Protocol (LDAP) distinguished name of the site, domain,
or OU of the link. For instance, for the `MyOU` organizational unit in the `contoso.com` domain, the
LDAP distinguished name is `ou=MyOU,dc=contoso,dc=com`.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.GroupPolicy.GpoLink

A GPO link between a GPO and a site, domain, or OU.

## OUTPUTS

### Microsoft.GroupPolicy.GpoLink

This cmdlet returns the GPO link after the change has been applied.

## NOTES

* You can use the **Domain** parameter to explicitly specify the domain for this cmdlet.

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

[New-GPLink](./New-GPLink.md)

[Remove-GPLink](./Remove-GPLink.md)

