---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
Module Name: GroupPolicy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/grouppolicy/new-gpo?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-GPO
---

# New-GPO

## SYNOPSIS

Creates a GPO.

## SYNTAX

### New (Default)

```
New-GPO [-Name] <String> [-Comment <String>] [-Domain <String>] [-Server <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### NewStarterGUID

```
New-GPO [-Name] <String> -StarterGpoGuid <Guid> [-Comment <String>] [-Domain <String>]
 [-Server <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NewStarterName

```
New-GPO [-Name] <String> -StarterGpoName <String> [-Comment <String>] [-Domain <String>]
 [-Server <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `New-GPO` cmdlet creates a GPO with a specified name. By default, the newly created GPO is not
linked to a site, domain, or organizational unit (OU).

You can use this cmdlet to create a GPO that is based on a starter GPO by specifying the GUID or the
display name of the Starter GPO, or by piping a **StarterGpo** object into the cmdlet.

The cmdlet returns a **GPO** object, which represents the created GPO that you can pipe to other
Group Policy cmdlets.

## EXAMPLES

### Example 1: Create a GPO in the domain of the user

```powershell
New-GPO -Name TestGPO -Comment "This is a test GPO."
```

```Output
DisplayName      : TestGPO 
DomainName       : contoso.com 
Owner            : CONTOSO\Domain Admins 
Id               : b8c1f2c2-fbd3-4a1f-94e1-3e156a65a29a 
GpoStatus        : AllSettingsEnabled 
Description      : This is a test GPO. 
CreationTime     : 3/2/2009 3:37:23 AM 
ModificationTime : 3/2/2009 3:37:22 AM 
UserVersion      : AD Version: 0, SysVol Version: 0 
ComputerVersion  : AD Version: 0, SysVol Version: 0 
WmiFilter        :
```

This command creates a GPO in the domain of the user. The GPO is created with the specified comment.

### Example 2: Create a GPO in the domain of the user that is pre-populated with the settings of the Starter GPO

```powershell
New-GPO -Name "FromStarterGPO" -StarterGPOName "Windows Vista EC Computer Starter GPO"
```

This command creates a GPO named FromStarterGPO in the domain of the user. The GPO is pre-populated
with the settings of the Starter GPO.

### Example 3: Create a GPO in the domain of the user and link it to an OU

```powershell
New-GPO -Name TestGPO | New-GPLink -Target "ou=Marketing,dc=contoso,dc=com" | 
    Set-GPPermissions -PermissionLevel gpoedit -TargetName "Marketing Admins" -TargetType Group 
```

```Output
DisplayName      : TestGPO 
DomainName       : contoso.com 
Owner            : CONTOSO\Domain Admins 
Id               : b8c1f2c2-fbd3-4a1f-94e1-3e156a65a29a 
GpoStatus        : AllSettingsEnabled 
Description      : 
CreationTime     : 3/2/2009 3:37:23 AM 
ModificationTime : 3/2/2009 3:37:22 AM 
UserVersion      : AD Version: 0, SysVol Version: 0 
ComputerVersion  : AD Version: 0, SysVol Version: 0 
WmiFilter        :
```

This command creates a GPO named `TestGPO`, links it to the `Marketing` OU in the `contoso.com`
domain, and grants the `Marketing Admins` security group permissions to edit the GPO.

A GPO object is returned by the command, so you could continue to configure the new GPO by piping
the output to other cmdlets. For example, you could set Registry preference items or registry-based
policy settings by piping the output to `Set-GPPrefRegistryValue` or to `Set-GPRegistryValue`.

## PARAMETERS

### -Comment

Includes a comment for the new GPO. The comment string must be enclosed in double- or
single-quotation marks and can contain 2,047 characters.

Use the comment to document the GPO and its implementation in your environment. Or, if you insert
keywords in the comment, you can use the keyword filter to find GPOs that have matching keywords.

```yaml
Type: System.String
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

For the `New-GPO` cmdlet:

- The new GPO is created in this domain.

- If a Starter GPO is specified, it must exist in this domain.

If you do not specify the **Domain** parameter, then the domain of the user running the current
session is used. If the cmdlet is being run from a computer startup or shutdown script, the domain
of the computer is used. For more information, see the Notes section in the full help.

If you specify a domain that is different from the domain of the user running the current session
(or the computer for a startup or shutdown script), then a trust must exist between that domain and
the domain of the user, or computer.

You can also refer to the **Domain** by its built-in alias, **DomainName**. For more information,
see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DomainName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Specifies a display name for the new GPO.

If another GPO with the same display name exists in the domain an error occurs.

You can also refer to the **Name** parameter by its built-in alias, **DisplayName**. For more
information, see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DisplayName

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server

Specifies the name of the domain controller that this cmdlet contacts to complete the operation. You
can specify either the fully qualified domain name (FQDN) or the host name.

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

### -StarterGpoGuid

Specifies a Starter GPO by its globally unique identifier (GUID). The GUID uniquely identifies the
Starter GPO. If a Starter GPO is specified, the GPO is created with its settings.

You can also refer to the **StarterGpoGuid** parameter by its built-in alias, **Id**. For more
information, see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: Guid
Parameter Sets: NewStarterGUID
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StarterGpoName

Specifies a Starter GPO by its display name. The name can contain 255 characters. If the name
includes blank characters, enclose the name in double-quotation marks or single-quotation marks. If
a Starter GPO is specified, the GPO is created with its settings.

The display name is not guaranteed to be unique in the domain. If another Starter GPO with the same
display name exists in the domain, an error occurs. You can use the **StarterGpoGuid** parameter to
uniquely identify a Starter GPO.

You can also refer to the **Name** parameter by its built-in alias, **DisplayName**. For more
information, see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: System.String
Parameter Sets: NewStarterName
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

### Microsoft.GroupPolicy.StarterGpo

You can pipe a Starter GPO that has predefined settings to this cmdlet.

## OUTPUTS

### Microsoft.GroupPolicy.Gpo

This cmdlet returns the GPO that was created.

## NOTES

* Only domain administrators, enterprise administrators, and members of the Group Policy creator
  owners group can create GPOs. These users must run Windows PowerShell in an elevated state.

  You can use the **Domain** parameter to explicitly specify the domain for this cmdlet.

  If you do not explicitly specify the domain, the cmdlet uses a default domain. The default domain
  is the domain that is used to access network resources by the security context under which the
  current session is running. This domain is typically the domain of the user that is running the
  session. For instance, the domain of the user who started the session by opening Windows
  PowerShell from the Program Files menu, or the domain of a user that is specified in a RunAs
  command. However, computer startup and shutdown scripts run under the context of the LocalSystem
  account. The LocalSystem account is a built-in local account, and it accesses network resources
  under the context of the computer account. Therefore, when this cmdlet is run from a startup or
  shutdown script, the default domain is the domain to which the computer is joined.

## RELATED LINKS

[Backup-GPO](./Backup-GPO.md)

[Copy-GPO](./Copy-GPO.md)

[Get-GPO](./Get-GPO.md)

[Import-GPO](./Import-GPO.md)

[Remove-GPO](./Remove-GPO.md)

[Rename-GPO](./Rename-GPO.md)

[Restore-GPO](./Restore-GPO.md)

