---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Restore-UevBackup
ms.reviewer:
ms.assetid: 95C9497A-684C-42F8-8592-833774522F94
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

### Example 1: Restore backed up settings from another computer
```
PS C:\>Restore-UevBackup -ComputerName "PattiFullerDevice03@Contoso.Com"
```

This command restores all backup packages from another computer.
The command sets a restore flag for all applications associated with the Backup profile on this computer.

## PARAMETERS

### -ComputerName
Specifies the fully qualified name of the computer from which to restore packages.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-UevTemplateProfile](./Set-UevTemplateProfile.md)

