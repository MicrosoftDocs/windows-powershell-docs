---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
Module Name: GroupPolicy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/grouppolicy/import-gpo?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-GPO
---

# Import-GPO

## SYNOPSIS

Imports the Group Policy settings from a backed-up GPO into a specified GPO.

## SYNTAX

### ImportGUID (Default)

```
Import-GPO -BackupId <Guid> -Path <String> [-TargetGuid <Guid>] [-TargetName <String>]
 [-MigrationTable <String>] [-CreateIfNeeded] [-Domain <String>] [-Server <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ImportName

```
Import-GPO -BackupGpoName <String> -Path <String> [-TargetGuid <Guid>] [-TargetName <String>]
 [-MigrationTable <String>] [-CreateIfNeeded] [-Domain <String>] [-Server <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Import-GPO` cmdlet imports the settings from a Group Policy Object (GPO) backup into a
specified target GPO. The target GPO can be in a different domain or forest than the backup that was
made and it does not have to exist prior to the operation.

Use the **Path** parameter to specify the location of the backup and then use the **BackupGpoName**
parameter to specify the GPO name of the backup to use, or the **BackupId** parameter to specify the
backup ID (GUID) of the backup to use.

If you specify a GPO name, the cmdlet imports the most recent backup. To import an earlier version
of a GPO backup, you must use the **BackupID** parameter to specify the unique backup ID for the
particular version. This is the GUID that uniquely identifies the backup within its backup
directory.

Use the **TargetName** parameter or the **TargetGuid** parameter to specify the target GPO into
which the settings should be imported. Use the optional **MigrationTable** parameter to map security
principals and Universal Naming Convention (UNC) paths across domains. Use the **CreateIfNeeded**
parameter to create a new GPO if the specified target GPO does not exist.

## EXAMPLES

### Example 1: Import the settings from the latest backup to another directory in the same domain

```powershell
Import-GPO -BackupGpoName 'TestGPO' -TargetName 'TestGPO' -path 'C:\backups'
```

```Output
DisplayName      : TestGPO
DomainName       : contoso.com
Owner            : CONTOSO\Domain Admins
Id               : 87d38d82-cc2d-4bf7-ad9f-4083a60316eb
GpoStatus        : AllSettingsEnabled
Description      :
CreationTime     : 3/3/2009 1:03:28 PM
ModificationTime : 3/6/2009 5:03:29 PM
UserVersion      : AD Version: 9, SysVol Version: 9
ComputerVersion  : AD Version: 5, SysVol Version: 5
WmiFilter        :
```

This command imports the settings from the most recent backup of the GPO named `TestGPO` in the
`c:\backups` directory into a GPO of the same name in the current domain. If a GPO named `TestGPO`
does not exist in the current domain, the command fails because the **CreateIfNeeded** parameter is
not specified.

### Example 2: Import the settings from specified backup in the same directory in the same domain

```powershell
$params = @{
    BackupId       = 'A491D730-F3ED-464C-B8C9-F50562C536AA'
    TargetName     = 'TestGPO'
    path           = 'C:\Backups'
    CreateIfNeeded = $true
}
Import-GPO @params
```

```Output
DisplayName      : TestGPO
DomainName       : contoso.com
Owner            : CONTOSO\Domain Admins
Id               : 87d38d82-cc2d-4bf7-ad9f-4083a60316eb
GpoStatus        : AllSettingsEnabled
Description      :
CreationTime     : 3/3/2009 1:03:28 PM
ModificationTime : 3/6/2009 5:11:49 PM
UserVersion      : AD Version: 10, SysVol Version: 10
ComputerVersion  : AD Version: 6, SysVol Version: 6
WmiFilter        :
```

This command imports the settings from the specified backup in the `C:\Backups` directory into a GPO
that is named `TestGPO` in the current domain. The **BackupId** parameter is used to specify the
GUID of the GPO backup to use. Because the **CreateIfNeeded** parameter is specified, if a GPO named
`TestGPO` does not exist in the current domain, one is created before the settings are imported.

### Example 3: Import the settings from the latest backup to another directory to the current domain

```powershell
$params = @{
    BackupGpoName  = 'TestGPO'
    Path           = 'D:\Backups'
    TargetName     = 'NewTestGPO'
    MigrationTable = 'D:\Tables\Migtable1.migtable'
    CreateIfNeeded = $true
}
Import-GPO @params
```

```Output
DisplayName      : NewTestGPO
DomainName       : contoso.com
Owner            : CONTOSO\Domain Admins
Id               : 87d38d82-cc2d-4bf7-ad9f-4083a60316eb
GpoStatus        : AllSettingsEnabled
Description      :
CreationTime     : 3/3/2009 1:03:28 PM
ModificationTime : 3/6/2009 5:11:49 PM
UserVersion      : AD Version: 1, SysVol Version: 1
ComputerVersion  : AD Version: 1, SysVol Version: 1
WmiFilter        :
```

This command imports the settings from the most recent backup of the GPO named `TestGPO` from the
`D:\Backups` directory to a GPO named `NewTestGPO` in the current domain. The specified migration
table is used to migrate security principals and UNC paths to the new GPO. Because the
**CreateIfNeeded** parameter is specified, the GPO is created if it does not already exist.

## PARAMETERS

### -BackupGpoName

Specifies the display name of the backed-up GPO from which this cmdlet imports the settings. The
most recent backup of the GPO is used. You can use the **BackupID** parameter to specify a particular
version to use when multiple backups of the same GPO exist in the backup directory.

You can also refer to the **BackupGpoName** parameter by its built-in alias, **DisplayName**. For
more information, see
[about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: System.String
Parameter Sets: ImportName
Aliases: DisplayName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -BackupId

Specifies the backup ID of a GPO backup. The backup ID is a globally unique identifier (GUID) that
uniquely identifies the backup. You can use this parameter to specify a particular version of a
backed-up GPO in the backup directory.

The backup ID is different from the ID of the GPO that was backed up.

You can also refer to the **BackupID** parameter by its built-in alias, **Id**. For more
information, see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: Guid
Parameter Sets: ImportGUID
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

### -CreateIfNeeded

Indicates that the cmdlet creates a GPO from the backup if the specified target GPO does not exist.

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

For the `Import-GPO` cmdlet, this is the domain into which you want to import the GPO.

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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MigrationTable

Specifies the path to a migration table file. You can use a migration table to map security
principals and UNC paths across domains.

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

### -Path

Specifies the path to the backup directory.

You can also refer to the **Path** parameter by its built-in aliases: **BackupLocation** or
**BackupDirectory**.

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
can specify either the fully qualified domain name (FQDN) or the host name

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

### -TargetGuid

Specifies the GUID of the GPO into which this cmdlet imports the settings. Use the *CreateIfNeeded*
parameter to force the GPO to be created if it does not already exist in the domain.

You must specify either the **TargetGuid** parameter or the **TargetName** parameter.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetName

Specifies the display name of the GPO into which the settings are to be imported. Use the
**CreateIfNeeded** parameter to force the GPO to be created if it does not already exist in the
domain.

You must specify either the **TargetGuid** parameter or the **TargetName** parameter.

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

### Microsoft.GroupPolicy.GpoBackup

You can pipe an object that represents a GPO backup on the file system to this cmdlet.

## OUTPUTS

### Microsoft.GroupPolicy.Gpo

This cmdlet returns an object that represents the GPO after the settings have been imported.

## NOTES

* You can use the `Import-GPO` to copy settings from a GPO backup in one domain to the same domain
  or another domain in the same or different forest.

  You can use the **Domain** parameter to explicitly specify the domain for this cmdlet.

  If you do not explicitly specify the domain, the cmdlet uses a default domain. The default domain
  is the domain that is used to access network resources by the security context under which the
  current session is running. This domain is typically the domain of the user that is running the
  session for example, the domain of the user who started the session by opening Windows PowerShell
  or the domain of a user that is specified in a runas command. However, computer startup and
  shutdown scripts run under the context of the LocalSystem account. The LocalSystem account is a
  built-in local account, and it accesses network resources under the context of the computer
  account. Therefore, when this cmdlet is run from a startup or shutdown script, the default domain
  is the domain to which the computer is joined.

## RELATED LINKS

[Backup-GPO](./Backup-GPO.md)

[Restore-GPO](./Restore-GPO.md)

