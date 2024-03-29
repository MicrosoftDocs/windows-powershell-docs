---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: https://learn.microsoft.com/powershell/module/webadministration/get-webconfigurationbackup?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WebConfigurationBackup

## SYNOPSIS
Gets a list of available IIS configuration backups.

## SYNTAX

```
Get-WebConfigurationBackup [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
Gets a list of available IIS configuration backups.

## EXAMPLES

### -------------- EXAMPLE 1: Get a list of the available IIS configuration backups --------------
```
IIS:\>Get-WebConfigurationBackup
```

Returns a list of available IIS configuration backups.

Name Creation Date

---- -------------

MyIISBackup 2/25/2009 12:00:00 AM

## PARAMETERS

### -Name
The name of an IIS Configuration backup to retrieve.
If a backup exists with the specified name, information about that backup is returned.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

