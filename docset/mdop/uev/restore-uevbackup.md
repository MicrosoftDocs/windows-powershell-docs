---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Restore-UevBackup
---

# Restore-UevBackup

## SYNOPSIS
Applies backed up settings from another computer to this computer.

## SYNTAX

```
Restore-UevBackup [-ComputerName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Restore-UevBackup** cmdlet allows all of the backed up settings from another computer to apply to this computer.
This cmdlet sets a restore flag for each user application that has a profile of Backup.
The next time that such an application runs, the backed up settings apply to the application.

## EXAMPLES

### Example 1: Restore backed up settings from another computermachinecomputer
```
PS C:\>Restore-UevBackup -MachineName "PattiFullerDevice03@Contoso.Com"
```

This command restores all backup packages from another computer.
The command sets a restore flag for all applications associated with the Backup profile on this computer.

## PARAMETERS

### -ComputerName
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

### -Confirm
Prompts you for confirmation before running the cmdlet.Prompts you for confirmation before running the cmdlet.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.Shows what would happen if the cmdlet runs.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-UevTemplateProfile](./Set-UevTemplateProfile.md)

