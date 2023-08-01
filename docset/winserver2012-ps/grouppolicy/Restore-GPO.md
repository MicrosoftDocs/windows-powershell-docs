---
external help file: GPv2_Cmdlets.xml
Module Name: GroupPolicy
online version: https://learn.microsoft.com/powershell/module/grouppolicy/restore-gpo?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Restore-GPO

## SYNOPSIS
Restores one GPO or all GPOs in a domain from one or more GPO backup files.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Restore-GPO [-Domain <String>] [-Server <String>] -BackupId <Guid> -Path <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Restore-GPO [-Domain <String>] [-Server <String>] [-All] -Path <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Restore-GPO [-Domain <String>] [-Server <String>] -Guid <Guid> -Path <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Restore-GPO [-Name] <String> [-Domain <String>] [-Server <String>] -Path <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The Restore-GPO cmdlet restores a GPO backup to the original domain from which it was saved.
If the original domain is not available, or if the GPO no longer exists in the domain, the cmdlet fails.

You can:

- Use the Guid parameter or the Name parameter to restore a GPO from its most recent backup.

- Use the All parameter to restore all GPOs in the domain from their most recent backups.

- Use the BackupId parameter to restore a GPO from a specific backup.
This parameter enables you to restore a GPO from a backup prior to the most recent one.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Restore-GPO -Name "TestGPO" -Path \\Server1\Backups
```

Description

-----------

This command restores the GPO named TestGpo from the \\\\Server1\Backups directory.
The most recent backup is restored.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Restore-GPO -GUID fa4a9473-6e2a-4b87-ab78-175e68d97bde -Path \\Server1\Backups
```

Description

-----------

This command restores the GPO with the GUID fa4a9473-6e2a-4b87-ab78-175e68d97bde from the \\\\Server1\Backups directory.
The most recent backup is restored.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Restore-GPO -All -Domain contoso.com -Path \\Server1\Backups
```

Description

-----------

This command restores all of the GPOs in the contoso.com domain previously backed up to \\\\Server1\Backup.
Each GPO is restored using its most recent backup.

If the domain of user that is running the session (or, for a startup or shutdown script, the domain of the computer) is different from the contoso.com domain, a trust must exist between the two domains or the command fails.

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>Restore-GPO -BackupId 0fc29b3c-fb83-4076-babb-6194c1b4fc26 -Path \\Server1\Backups
```

Description

-----------

This command restores a GPO from the backup specified by the BackupId parameter.
The BackupId parameter can be used to restore a GPO from a backup prior to the most recent backup.

## PARAMETERS

### -All
Restores all GPOs in the domain that have backups in the backup directory.
Each GPO is restored from its most recent backup in the directory.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackupId
Specifies the backup ID of a GPO backup.
The backup ID is a globally unique identifier (GUID) that uniquely identifies the backup.
You can use this parameter to specify a particular version of a backed-up GPO in the backup directory.

Note: The backup ID is different from the ID of the GPO that was backed up (specified by the Guid parameter).

```yaml
Type: Guid
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Domain
Specifies the domain for this cmdlet.
You must specify the fully qualified domain name (FQDN) of the domain (for example: sales.contoso.com).

For the Restore-GPO cmdlet, this is the domain in which you want to restore the GPO.
This must be the domain from which the GPO was backed up.

If you do not specify the Domain parameter, the domain of the user that is running the current session is used.
(If the cmdlet is being run from a computer startup or shutdown script, the domain of the computer is used.) For more information, see the Notes section in the full Help.

If you specify a domain that is different from the domain of the user that is running the current session (or, for a startup or shutdown script, the computer), a trust must exist between that domain and the domain of the user (or the computer).

You can also refer to the Domain parameter by its built-in alias, "domainname".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Guid
Specifies the GPO to restore by its globally unique identifier (GUID).
The GUID uniquely identifies the GPO.

The GPO is restored from its most recent backup in the backup directory.
To specify a different backup than the most recent backup, use the BackupId parameter.

You can also refer to the Guid parameter by its built-in alias, "id".
For more information, see about_Aliases.

```yaml
Type: Guid
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the GPO to restore by its display name.
The GPO is restored from its most recent backup in the backup directory.
To specify a different backup than the most recent backup, use the BackupId parameter.

The display name is not guaranteed to be unique in the domain.
If another GPO with the same display name exists in the domain an error occurs.
You can use the Guid parameter to uniquely identify a GPO.

You can also refer to the Name parameter by its built-in alias, "displayname".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path to the backup directory.

You can also refer to the Path parameter by its built-in alias, "backuplocation".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.GroupPolicy.BackupGpo
A GPO backup, a separate file that holds the settings of a GPO that can be imported elsewhere to recreate the GPO.

## OUTPUTS

### Microsoft.GroupPolicy.Gpo
Restore-GPO returns the restored GPO.

## NOTES
* You can use the Domain parameter to explicitly specify the domain for this cmdlet.

  If you do not explicitly specify the domain, the cmdlet uses a default domain.
The default domain is the domain that is used to access network resources by the security context under which the current session is running.
This domain is typically the domain of the user that is running the session.
For example, the domain of the user who started the session by opening Windows PowerShell from the Program Files menu, or the domain of a user that is specified in a runas command.
However, computer startup and shutdown scripts run under the context of the LocalSystem account.
The LocalSystem account is a built-in local account, and it accesses network resources under the context of the computer account.
Therefore, when this cmdlet is run from a startup or shutdown script, the default domain is the domain to which the computer is joined.

## RELATED LINKS

[Backup-GPO](./Backup-GPO.md)

