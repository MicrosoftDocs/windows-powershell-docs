---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/27/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Restore-WebConfiguration
ms.reviewer:
ms.assetid: 81C2DCCF-49AF-4948-97B3-EE9EEE723B64
---

# Restore-WebConfiguration

## SYNOPSIS
Restores an IIS configuration backup.

## SYNTAX

```
Restore-WebConfiguration [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Restore-WebConfiguration** cmdlet restores an Internet Information Services (IIS) configuration backup that was created by using the Backup-WebConfiguration cmdlet.

## EXAMPLES

### Example 1: Restore a backup
```
IIS:\> Restore-WebConfiguration -Name "MyBackup"
```

This command restores the IIS configuration backup named MyBackup.

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
Specifies the name of the backup.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WebConfiguration](./Add-WebConfiguration.md)

[Backup-WebConfiguration](./Backup-WebConfiguration.md)

[Clear-WebConfiguration](./Clear-WebConfiguration.md)

[Get-WebConfiguration](./Get-WebConfiguration.md)

[Select-WebConfiguration](./Select-WebConfiguration.md)

[Set-WebConfiguration](./Set-WebConfiguration.md)

[Get-WebConfigurationBackup](./Get-WebConfigurationBackup.md)

[Remove-WebConfigurationBackup](./Remove-WebConfigurationBackup.md)

