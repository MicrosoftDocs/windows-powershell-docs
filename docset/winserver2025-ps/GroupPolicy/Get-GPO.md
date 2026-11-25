---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
Module Name: GroupPolicy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/grouppolicy/get-gpo?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-GPO
---

# Get-GPO

## SYNOPSIS

Gets one GPO or all the GPOs in a domain.

## SYNTAX

### ByGUID (Default)

```
Get-GPO [-Guid] <Guid> [[-Domain] <String>] [[-Server] <String>] [-All] [<CommonParameters>]
```

### ByName

```
Get-GPO [-Name] <String> [[-Domain] <String>] [[-Server] <String>] [-All] [<CommonParameters>]
```

### GetAll

```
Get-GPO [[-Domain] <String>] [[-Server] <String>] [-All] [<CommonParameters>]
```

## DESCRIPTION

The `Get-GPO` cmdlet gets one Group Policy Object (GPO) or all the GPOs in a domain. You can
specify a GPO by its display name or by its globally unique identifier (GUID) to get a single GPO,
or you can get all the GPOs in the domain through the **All** parameter.

This cmdlet returns one or more objects that represent the requested GPOs. By default, properties of
the requested GPOs are printed to the display; however, you can also pipe the output of the
`Get-GPO` cmdlet to other Group Policy cmdlets.

## EXAMPLES

### Example 1: Get a single GPO from a domain

```powershell
Get-GPO -Name "Group Policy Test"
```

```Output
DisplayName      : Group Policy Test
DomainName       : contoso.com
Owner            : CONTOSO\Domain Admins
Id               : 31a09564-cd4a-4520-98fa-446a2af23b4b
GpoStatus        : AllSettingsEnabled
Description      :
CreationTime     : 2/26/2009 12:15:42 AM
ModificationTime : 2/26/2009 12:15:42 AM
UserVersion      : AD Version: 0, SysVol Version: 0
ComputerVersion  : AD Version: 0, SysVol Version: 0
WmiFilter        :
```

### Example 2: Get a single GPO by GUID

This command gets the GPO named `Group Policy Test`. The GPO must exist in the domain of the user
that is running the session (or, for startup and shutdown scripts, the computer). The command gets
the GPO information by contacting the primary domain controller (PDC).

```powershell
Get-GPO -Guid 31a09564-cd4a-4520-98fa-446a2af23b4b -Domain "sales.contoso.com"
```

```Output
DisplayName      : Group Policy Test
DomainName       : sales.contoso.com
Owner            : SALES\Domain Admins
Id               : 31a09564-cd4a-4520-98fa-446a2af23b4b
GpoStatus        : AllSettingsEnabled
Description      :
CreationTime     : 2/26/2009 12:15:42 AM
ModificationTime : 2/26/2009 12:15:42 AM
UserVersion      : AD Version: 0, SysVol Version: 0
ComputerVersion  : AD Version: 0, SysVol Version: 0
WmiFilter        :
```

This command gets the GPO that has the ID (GUID) `331a09564-cd4a-4520-98fa-446a2af23b4b` in the
`sales.contoso.com` domain. If the domain of the user that is running the session (or, for startup
and shutdown scripts, the computer) is different that `sales.contoso.com`, a trust must exist
between the two domains. The command retrieves the GPO information by contacting the PDC (in the
`sales.contoso.com` domain).

### Example 3: Get all GPOs from a domain

```powershell
Get-GPO -All -Domain "sales.contoso.com"
```

This command get all the GPOs in the `sales.contoso.com` domain.

## PARAMETERS

### -All

Indicates that the cmdlet gets all the GPOs in the domain.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Domain

Specifies the domain for this cmdlet. You must specify the fully qualified domain name (FQDN) of the
domain.

For the `Get-GPO` cmdlet, the GPO (or GPOs) to that this cmdlet gets must exist in this domain.

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
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Guid

Specifies the GPO to retrieve by its globally unique identifier (GUID). The GUID uniquely identifies
the GPO.

You can also refer to the **Guid** parameter by its built-in alias, **Id**.

```yaml
Type: Guid
Parameter Sets: ByGUID
Aliases: Id

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Specifies the GPO to retrieve by its display name.

The display name is not guaranteed to be unique in the domain. If another GPO with the same display
name exists in the domain an error occurs. You can use the **Guid** parameter to uniquely identify a
GPO.

You can also refer to the **Name** parameter by its built-in alias, **DisplayName**.

```yaml
Type: System.String
Parameter Sets: ByName
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

If you do not specify the name by using the **Server** parameter, the primary domain controller
(PDC) emulator is contacted.

You can also refer to the **Server** parameter by its built-in alias, **DC**.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DC

Required: False
Position: 2
Default value: None
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

You can pipe a GPO for which to get information to this cmdlet. You can pipe GPO objects into this
cmdlet to display information about the GPOs. Collections that contain GPOs from different domains
are not supported.

## OUTPUTS

### Microsoft.GroupPolicy.Gpo

This cmdlet returns an object that represents the requested GPO.

## NOTES

- You can use the **Domain** parameter to explicitly specify the domain for this cmdlet.

  If you do not explicitly specify the domain, the cmdlet uses a default domain. The default domain
  is the domain that is used to access network resources by the security context under which the
  current session is running. This domain is typically the domain of the user that is running the
  session. For example, the domain of the user who started the session by opening Windows PowerShell
  from the Program Files menu, or the domain of a user that is specified in a runas command.
  However, computer startup and shutdown scripts run under the context of the LocalSystem account.
  The LocalSystem account is a built-in local account, and it accesses network resources under the
  context of the computer account. Therefore, when this cmdlet is run from a startup or shutdown
  script, the default domain is the domain to which the computer is joined.

  Only one domain can be used by an instance of this cmdlet. If you pipe a collection of GPO
  (**Microsoft.GroupPolicy.Gpo**) objects to this cmdlet, the **DomainName** property of the first
  GPO object in the collection specifies the domain for the cmdlet. This is because **domainname**
  is a built-in alias for the **Domain** parameter, and the **Domain** parameter can take its value
  by property name from the pipeline. A non-terminating error occurs for any GPOs in the collection
  that are not in this domain. If this domain is different from the domain of the user account (for
  startup or shutdown scripts, the computer account), a trust must exist between the two domains.

## RELATED LINKS

[Backup-GPO](./Backup-GPO.md)

[Copy-GPO](./Copy-GPO.md)

[Import-GPO](./Import-GPO.md)

[New-GPO](./New-GPO.md)

[Remove-GPO](./Remove-GPO.md)

[Rename-GPO](./Rename-GPO.md)

[Restore-GPO](./Restore-GPO.md)
