---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
Module Name: GroupPolicy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/grouppolicy/rename-gpo?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-GPO
---

# Rename-GPO

## SYNOPSIS

Assigns a new display name to a GPO.

## SYNTAX

### RenameByGUID (Default)

```
Rename-GPO -Guid <Guid> -TargetName <String> [-Domain <String>] [-Server <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### RenameByName

```
Rename-GPO [-Name] <String> -TargetName <String> [-Domain <String>] [-Server <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Rename-GPO` cmdlet assigns a different, non-null display name to a Group Policy Object (GPO).
This cmdlet has no effect on the GUID of the GPO.

## EXAMPLES

### Example 1: Rename a GPO

```powershell
Rename-GPO -Name "SampleGPO" -TargetName "SecurityGPO"
```

```Output
DisplayName      : securityGPO
DomainName       : contoso.com
Owner            : CONTOSO\Domain Admins
Id               : 2c08f9b5-32c3-43fa-af8f-f1939b1ac8a0
GpoStatus        : AllSettingsEnabled
Description      :
CreationTime     : 3/6/2009 4:20:25 PM
ModificationTime : 3/6/2009 4:20:24 PM
UserVersion      : AD Version: 0, SysVol Version: 0
ComputerVersion  : AD Version: 0, SysVol Version: 0
WmiFilter        :
```

This command renames the GPO named `SampleGPO` to `SecurityGPO`.

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

For the `Rename-GPO` cmdlet, this is the domain of the GPO that you want to rename.

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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Guid

Specifies the GPO to rename by its globally unique identifier (GUID). The GUID uniquely identifies
the GPO.

You can also refer to the **Guid** parameter by its built-in alias, **Id**.

```yaml
Type: Guid
Parameter Sets: RenameByGUID
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Specifies the GPO to rename by its current display name.

The display name is not guaranteed to be unique in the domain. If another GPO with the same display
name exists in the domain, an error occurs. You can use the **Guid** parameter to uniquely identify
a GPO.

You can also refer to the Name parameter by its built-in alias, **DisplayName**.

```yaml
Type: System.String
Parameter Sets: RenameByName
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
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetName

Specifies the new display name of the GPO. Because the display name may not be unique, an error is
returned if another GPO in the domain has the same display name.

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

You can pipe a **GPO** object to the GPO to rename. Collections that contain GPOs from different
domains are not supported.

## OUTPUTS

### Microsoft.GroupPolicy.Gpo

This cmdlet returns the GPO with the new display name.

## NOTES

* You can use the **Domain** parameter to explicitly specify the domain for this cmdlet.

  If you do not explicitly specify the domain, the cmdlet uses a default domain. The default domain
  is the domain that is used to access network resources by the security context under which the
  current session is running. This domain is typically the domain of the user that is running the
  session. For example, the domain of the user who started the session by opening Windows PowerShell
  from the Program Files menu, or the domain of a user that is specified in a runas command.
  However, computer startup and shutdown scripts run under the context of the LocalSystem account.
  The LocalSystem account is a built-in local account, and it accesses network resources under the
  context of the computer account. Therefore, when this cmdlet is run from a startup or shutdown
  script, the default domain is the domain to which the computer is joined.

## RELATED LINKS

[Backup-GPO](./Backup-GPO.md)

[Copy-GPO](./Copy-GPO.md)

[Get-GPO](./Get-GPO.md)

[Import-GPO](./Import-GPO.md)

[New-GPO](./New-GPO.md)

[Remove-GPO](./Remove-GPO.md)

[Restore-GPO](./Restore-GPO.md)

