---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
Module Name: GroupPolicy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/grouppolicy/remove-gplink?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-GPLink
---

# Remove-GPLink

## SYNOPSIS

Removes a GPO link from a site, domain or OU.

## SYNTAX

### LinkbyGUID (Default)

```
Remove-GPLink -Guid <Guid> -Target <String> [-Domain <String>] [-Server <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### LinkbyName

```
Remove-GPLink [-Name] <String> -Target <String> [-Domain <String>] [-Server <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Remove-GPLink` cmdlet removes the link between a Group Policy Object (GPO) and a specified
site, domain, or OU. This cmdlet does not delete the actual GPO or any other links between the
specified GPO and other sites, domains, or OUs.

## EXAMPLES

### Example 1: Remove the specified GPO link

```powershell
Remove-GPLink -Name "MyGPO" -Target "OU=MyOU,dc=contoso,dc=com"
```

```Output
DisplayName      : MyGPO
DomainName       : contoso.com
Owner            : CONTOSO\Domain Admins
Id               : 375865b2-3b5f-480f-8f56-2a994ea6e725
GpoStatus        : AllSettingsEnabled
Description      :
CreationTime     : 2/26/2009 11:28:08 PM
ModificationTime : 3/5/2009 3:36:34 PM
UserVersion      : AD Version: 0, SysVol Version: 0
ComputerVersion  : AD Version: 1, SysVol Version: 1
WmiFilter        :
```

This command removes the link between the GPO named `MyGPO` and the `MyOU` organizational unit in
the `contoso.com` domain.

### Example 2: Remove the link between the specified GPO and the default site

```powershell
Remove-GPLink -Name "MyGPO" -Target "Default-First-Site-Name"
```

This command removes the link between the GPO named MyGPO and the default site.

### Example 3: Remove the links for all GPOs that are linked to the specified organizational unit

```powershell
(Get-GPInheritance -Target "ou=MyOU,dc=contoso,dc=com").GpoLinks | Remove-GPLink
```

```Output
DisplayName      : TestGPO-3
DomainName       : contoso.com
Owner            : CONTOSO\Domain Admins
Id               : d02126d4-82e8-4e87-b4a0-2d44b6891411
GpoStatus        : AllSettingsEnabled
Description      :
CreationTime     : 2/27/2009 2:59:51 PM
ModificationTime : 3/5/2009 3:36:37 PM
UserVersion      : AD Version: 13, SysVol Version: 13
ComputerVersion  : AD Version: 0, SysVol Version: 0
WmiFilter        :

DisplayName      : TestGPO-2
DomainName       : contoso.com
Owner            : CONTOSO\Domain Admins
Id               : 375865b2-3b5f-480f-8f56-2a994ea6e725
GpoStatus        : AllSettingsEnabled
Description      :
CreationTime     : 2/26/2009 11:28:08 PM
ModificationTime : 3/5/2009 3:36:34 PM
UserVersion      : AD Version: 0, SysVol Version: 0
ComputerVersion  : AD Version: 1, SysVol Version: 1
WmiFilter        :
```

This command removes the links for all the GPOs that are linked to the `MyOU` organizational unit in
the `contoso.com` domain.

This cmdlet is used to get a **Microsoft.GroupPolicy.Som** object for the OU. The GpoLinks property
of the SOM object contains all the GPO links for GPOs that are linked to the OU. Links that are
inherited from higher-level containers are not included. This collection is piped into
`Remove-GPLink`. The GPOs for which links have been removed are returned.

## PARAMETERS

### -Domain

Specifies the domain for this cmdlet. You must specify the fully qualified domain name (FQDN) of the
domain.

For the `Remove-GPLink` cmdlet:

- The GPO that is linked must exist in this domain.

- The Active Directory container (site, domain, or OU) that is linked must exist in a domain that
  has a trust relationship with this domain.

Note: To specify a domain to link to, use the **Target** parameter.

If you do not specify the **Domain** parameter, the domain of the user that is running the current
session is used. If the cmdlet is being run from a computer startup or shutdown script, the domain
of the computer is used. For more information, see the Notes section in the full Help.

If you specify a domain that is different from the domain of the user that is running the current
session (or, for a startup or shutdown script, the computer), a trust must exist between that domain
and the domain of the user, or the computer.

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

### -Guid

Specifies the GPO for which to remove the link by its globally unique identifier (GUID).
The `GUID` uniquely identifies the GPO.

You can also refer to the **Guid** parameter by its built-in aliases, **id** and **gpoid**. For more
information, see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: Guid
Parameter Sets: LinkbyGUID
Aliases: ID, GPOID

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Specifies the GPO for which to remove the link by its display name.

The display name is not guaranteed to be unique in the domain. If another GPO with the same display
name exists in the domain an error occurs. You can use the **Guid** parameter to uniquely identify a
GPO.

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

### -Server

Specifies the name of the domain controller that this cmdlet contacts to complete the operation. You
can specify either the fully qualified domain name (FQDN) or the host name.

If you do not specify the name using the **Server** parameter, the primary domain controller (PDC)
emulator is contacted.

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

Specifies the Lightweight Directory Access Protocol (LDAP) distinguished name of the site, domain,
or OU from which to remove the link. For instance, for the `MyOU` organizational unit in the
`contoso.com` domain, the LDAP distinguished name is `ou=MyOU,dc=contoso,dc=com`.

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

This cmdlet accepts an object that represents the link between a GPO and a site, domain, or OU.

## OUTPUTS

### Microsoft.GroupPolicy.Gpo

This cmdlet returns the GPO for which the link has been removed.

## NOTES

## RELATED LINKS

[New-GPLink](./New-GPLink.md)

[Set-GPLink](./Set-GPLink.md)
