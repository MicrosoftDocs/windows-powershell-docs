---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
Module Name: GroupPolicy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/grouppolicy/backup-gpo?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Backup-GPO
---

# Backup-GPO

## SYNOPSIS

Backs up one GPO or all the GPOs in a domain.

## SYNTAX

### BackupOne(GUID) (Default)

```
Backup-GPO -Guid <Guid> -Path <String> [-Comment <String>] [-Domain <String>] [-Server <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BackupOne(Name)

```
Backup-GPO [-Name] <String> -Path <String> [-Comment <String>] [-Domain <String>]
 [-Server <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BackupAll

```
Backup-GPO -Path <String> [-Comment <String>] [-Domain <String>] [-Server <String>] [-All]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Backup-GPO` cmdlet backs up a specified Group Policy Object (GPO) or all the GPOs in a domain
to a backup directory. The backup directory and GPO must already exist.

## EXAMPLES

### Example 1: Backup a GPO to a specific directory

```powershell
Backup-Gpo -Name TestGPO -Path C:\GpoBackups -Comment "Weekly Backup"
```

```output
DisplayName     : TestGPO
GpoId           : 35c12ab3-956c-45d5-973b-46b17d225f47
Id              : 2b509d4e-40f5-4337-82f7-458584555d0c
BackupDirectory : C:\GpoBackups
CreationTime    : 2/25/2009 8:48:19 PM
DomainName      : contoso.com
Comment         : Weekly Backup
```

This command backs up the `TestGPO` GPO to the `C:\GpoBackups` directory.
The specified comment is included in the GPO backup.

### Example 2: Backup a GPO with the specified GUID to a directory

```powershell
$params = @{
    GUID   = 'fa4a9473-6e2a-4b87-ab78-175e68d97bde'
    Domain = 'contoso.com'
    Server   = 'DC1'
    Path = '\\Server1\GpoBackups'
}
Backup-Gpo @params
```

This command backs up the GPO with the specified **GUID** in the `contoso.com` domain to the
`\\Server1\GpoBackups` directory. The domain controller at `DC1` is contacted to complete
the operation.

If the domain of the user running the session (or, for startup and shutdown scripts, the computer)
is different from the `contoso.com` domain, a trust must exist between the two domains or the
command fails.

### Example 3: Backup all GPOs in the domain of the user that is running the session

```powershell
Backup-Gpo -All -Path "\\Server1\GpoBackups"
```

This command backs up all the GPOs in the domain of the user that is running the session (or, for
startup and shutdown scripts, the computer) to the `\\Server1\GpoBackups` directory.

## PARAMETERS

### -All

Specifies that all the GPOs in the domain are backed up.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: BackupAll
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Comment

Specifies a comment for the backed-up GPO. The comment string must be enclosed in double-quotation
or single-quotation marks and can contain 2,047 characters.

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
domain (for example: sales.contoso.com).

For the **Backup-GPO** cmdlet, the GPO to back up must exist in this domain.

If you do not specify the **Domain** parameter, the domain of the user that is running the current
session is used. (If the cmdlet is being run from a computer startup or shutdown script, the domain
of the computer is used.) For more information, see the Notes section in the full Help.

If you specify a domain that is different from the domain of the user that is running the current
session (or, for a startup or shutdown script, the computer), a trust must exist between that domain
and the domain of the user (or the computer).

You can also refer to Domain by its built-in alias, domain name. For more information, see
[about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases)

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

Specifies the GPO to backup by its globally unique identifier (GUID).
The GUID uniquely identifies the GPO.

You can also refer to the **Guid** parameter by its built-in alias, **Id**. For more information,
see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: Guid
Parameter Sets: BackupOne(GUID)
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Specifies the GPO to backup by its display name.

The display name is not guaranteed to be unique in the domain.
If another GPO with the same display name exists in the domain an error occurs.
You can use the **Guid** parameter to uniquely identify a GPO.

You can also refer to the Name parameter by its built-in alias, **DisplayName**. For more
information, see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: System.String
Parameter Sets: BackupOne(Name)
Aliases: DisplayName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Path

Specifies the path to the backup directory; for instance, `C:\Backups` or `\\MyServer\Backups`.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: BackupLocation

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server

Specifies the name of the domain controller that this cmdlet contacts to complete the operation.
You can specify either the fully qualified domain name (FQDN) or the host name.

If you do not specify the name by using the **Server** parameter, the PDC emulator is contacted.

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

Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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

A GPO to be backed up.
Collections that contain GPOs from different domains are not supported.

## OUTPUTS

### Microsoft.GroupPolicy.GpoBackup

This cmdlet returns an object that represents the file that holds the settings of the backed-up GPO.

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

[Import-GPO](./Import-GPO.md)

[Restore-GPO](./Restore-GPO.md)

