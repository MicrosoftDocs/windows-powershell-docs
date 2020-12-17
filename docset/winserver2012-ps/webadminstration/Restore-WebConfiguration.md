---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: 81C2DCCF-49AF-4948-97B3-EE9EEE723B64
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Restore-WebConfiguration

## SYNOPSIS
Restores an IIS configuration backup.

## SYNTAX

```
Restore-WebConfiguration [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Restores an IIS configuration backup that was created by using theT:Microsoft.IIs.PowerShell.Provider.Backup-WebConfigurationcmdlet.

## EXAMPLES

### -------------- EXAMPLE 1: Restoring a backup --------------
```
IIS:\>Restore-WebConfiguration -Name MyBackup
```

Restores the IIS configuration backup named MyBackup.

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
The name of the backup to restore.

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

