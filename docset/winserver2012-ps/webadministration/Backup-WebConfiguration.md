---
author: Kateyanne
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
manager: dansimp
Module Name: WebAdministration
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/webadministration/backup-webconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Backup-WebConfiguration

## SYNOPSIS
Creates a backup of an IIS configuration.

## SYNTAX

```
Backup-WebConfiguration [-Name] <String> [<CommonParameters>]
```

## DESCRIPTION
Creates a backup of an IIS configuration.
A folder named with the value of theNameparameter is created for the backup in the $env:Windir\System32\inetsrv\backup folder.

## EXAMPLES

### -------------- EXAMPLE 1: Backing up an IIS configuration --------------
```
IIS:\>Backup-WebConfiguration -Name MyIISBackup
```

Demonstrates how to create a backup of your IIS configuration in a folder named "MyIISBackup".

Name Creation Date

---- -------------

MyIISBackup 2/20/2009 12:00:00 AM

## PARAMETERS

### -Name
The name of the folder created to store the backup files.
If a backup with the name specified already exists, an error is returned.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

[Restore-WebConfiguration](./Restore-WebConfiguration.md)

