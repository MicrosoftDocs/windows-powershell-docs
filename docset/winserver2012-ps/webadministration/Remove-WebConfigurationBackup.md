---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: https://learn.microsoft.com/powershell/module/webadministration/remove-webconfigurationbackup?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-WebConfigurationBackup

## SYNOPSIS
Removes an existing IIS configuration backup.

## SYNTAX

```
Remove-WebConfigurationBackup [[-Name] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Removes an IIS configuration backup that was created by using theT:Microsoft.IIs.PowerShell.Provider.Backup-WebConfigurationcmdlet.

## EXAMPLES

### -------------- EXAMPLE 1: Adding and removing an IIS configuration backup --------------
```
IIS:\>Backup-WebConfiguration MyNewBackup Get-WebConfigurationBackup MyNewBackup sleep 5 Remove-WebConfigurationBackup MyNewBackup
```

The example creates a configuration backup, lists the backup created, sleeps for 5 seconds, and then removes the backup.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
The name of the configuration backup that is to be removed.
The folder with this name is deleted from the $env:Windir\system32\inetsrv\backup folder.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

