---
external help file: NetworkControllerFc-help.xml
Module Name: NetworkControllerFc
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/networkcontrollerfc/restore-networkcontrolleronfailovercluster?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-NetworkControllerOnFailoverCluster
---

# Restore-NetworkControllerOnFailoverCluster

## SYNOPSIS

Restores the NetworkController from a Backup.

## SYNTAX

```
Restore-NetworkControllerOnFailoverCluster [-BackupPath] <String> [[-IsSfNcBackup] <Boolean>]
 [<CommonParameters>]
```

## DESCRIPTION

Restores the NetworkController state from a previous Backup. This performs the following tasks.

- Extracts the REST resources form the Backup.
- Cleans up the state of all the MicroServices and restarts the services .
- Replays the REST resources.

## EXAMPLES

### Example 1

```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -BackupPath

The Folder path where the NetworkController Backup is stored.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsSfNcBackup

True if this is a Service Fabric Based backup.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
