---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
Module Name: GroupPolicy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/grouppolicy/restore-gpo?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-GPO
---

# Restore-GPO

## SYNOPSIS

Restores one GPO or all GPOs in a domain from one or more GPO backup files.

## SYNTAX

### RestoreFromBackupId (Default)

```
Restore-GPO -BackupId <Guid> -Path <String> [-Domain <String>] [-Server <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### RestoreFromGpo(GUID)

```
Restore-GPO -Guid <Guid> -Path <String> [-Domain <String>] [-Server <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### RestoreFromGpo(Name)

```
Restore-GPO [-Name] <String> -Path <String> [-Domain <String>] [-Server <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### RestoreAll

```
Restore-GPO -Path <String> [-Domain <String>] [-Server <String>] [-All] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The `Restore-GPO` cmdlet restores a Group Policy Object (GPO) backup to the original domain from
which it was saved. If the original domain is not available, or if the GPO no longer exists in the
domain, the cmdlet fails.

You can:

- Use the **Guid** parameter or the *Name* parameter to restore a GPO from its most recent backup.

- Use the **All** parameter to restore all GPOs in the domain from their most recent backups.

- Use the **BackupID** parameter to restore a GPO from a specific backup.
This parameter enables you to restore a GPO from a backup prior to the most recent one.

## EXAMPLES

### Example 1: Restore a GPO from a directory

```powershell
Restore-GPO -Name "TestGPO" -Path "\\Server1\Backups"
```

This command restores the GPO named `TestGPO` from the `\\Server1\Backups` directory. The most recent
backup is restored.

### Example 2: Restore a GPO from a directory using the GPOs GUID

```powershell
Restore-GPO -GUID fa4a9473-6e2a-4b87-ab78-175e68d97bde -Path "\\Server1\Backups"
```

This command restores the GPO with the GUID `fa4a9473-6e2a-4b87-ab78-175e68d97bde` from the
`\\Server1\Backups` directory. The most recent backup is restored.

### Example 3: Restore all GPOs in a domain that were previously backed up to a directory

```powershell
Restore-GPO -All -Domain "contoso.com" -Path "\\Server1\Backups"
```

This command restores all of the GPOs in the `contoso.com` domain previously backed up to
`\\Server1\Backup`. Each GPO is restored using its most recent backup.

If the domain of user that is running the session (or, for a startup or shutdown script, the domain
of the computer) is different from the `contoso.com` domain, a trust must exist between the two
domains or the command fails.

### Example 4: Restore a GPO using its backup ID

```powershell
Restore-GPO -BackupId 0fc29b3c-fb83-4076-babb-6194c1b4fc26 -Path "\\Server1\Backups"
```

This command restores a GPO from the backup specified by the **BackupID** parameter. The
**BackupID** parameter can be used to restore a GPO from a backup prior to the most recent backup.

## PARAMETERS

### -All

Indicates that the cmdlet restores all GPOs in the domain that have backups in the backup directory.
Each GPO is restored from its most recent backup in the directory.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RestoreAll
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackupId

Specifies the backup ID of a GPO backup. The backup ID is a globally unique identifier (GUID) that
uniquely identifies the backup. You can use this parameter to specify a particular version of a
backed-up GPO in the backup directory.

The backup ID is different from the ID of the GPO that was backed up (specified by the **Guid**
parameter), you can find the backup ID in the backup directory.

```yaml
Type: Guid
Parameter Sets: RestoreFromBackupId
Aliases: Id

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

### -Domain

Specifies the domain for this cmdlet. You must specify the fully qualified domain name (FQDN) of the
domain.

For the `Restore-GPO` cmdlet, this is the domain in which you want to restore the GPO. This must
be the domain from which the GPO was backed up.

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

Specifies the GPO to restore by its globally unique identifier (GUID). The GUID uniquely identifies
the GPO.

The GPO is restored from its most recent backup in the backup directory. To specify a different
backup than the most recent backup, use the **BackupID** parameter.

You can also refer to the **Guid** parameter by its built-in alias, **Id**.

```yaml
Type: Guid
Parameter Sets: RestoreFromGpo(GUID)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Specifies the GPO to restore by its display name. The GPO is restored from its most recent backup in
the backup directory. To specify a different backup than the most recent backup, use the BackupId
parameter.

The display name is not guaranteed to be unique in the domain. If another GPO with the same display
name exists in the domain an error occurs. You can use the **Guid** parameter to uniquely identify a
GPO.

You can also refer to the Name parameter by its built-in alias, **DisplayName**.

```yaml
Type: System.String
Parameter Sets: RestoreFromGpo(Name)
Aliases: DisplayName

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Specifies the path to the backup directory.

You can also refer to the **Path** parameter by its built-in alias, **BackupLocation**.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: BackupLocation, BackupDirectory

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.GroupPolicy.BackupGpo

You can pipe a GPO backup, a separate file that holds the settings of a GPO that can be imported
elsewhere to recreate the GPO to this cmdlet.

## OUTPUTS

### Microsoft.GroupPolicy.Gpo

This cmdlet returns the restored GPO.

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

[Backup-GPO](./Backup-GPO.md)

[Copy-GPO](./Copy-GPO.md)

[Get-GPO](./Get-GPO.md)

[Import-GPO](./Import-GPO.md)

[New-GPO](./New-GPO.md)

[Remove-GPO](./Remove-GPO.md)

[Rename-GPO](./Rename-GPO.md)

