---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: Remove-WebConfigurationBackup
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 6186AB69-EFC1-4CFD-A170-41DB868A559E
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Remove-WebConfigurationBackup

## SYNOPSIS
Removes an existing IIS configuration backup.

## SYNTAX

```
Remove-WebConfigurationBackup [[-Name] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WebConfigurationBackup** cmdlet removes an Internet Information Services (IIS) configuration backup that was created by using the Backup-WebConfiguration cmdlet.

## EXAMPLES

### Example 1: Adding and removing an IIS configuration backup
```
IIS:\>Backup-WebConfiguration -Name "MyNewBackup" 
IIS:\> Get-WebConfigurationBackup -Name "MyNewBackup" 
IIS:\> sleep 5 
IIS:\> Remove-WebConfigurationBackup -Name "MyNewBackup"
```

This example creates a configuration backup, lists the backup created, sleeps for 5 seconds, and then removes the backup.

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
Specifies the name of the configuration backup that this cmdlet removes.
This cmdlet deletes the folder with this name from the $env:Windir\system32\inetsrv\backup folder.

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

[Backup-WebConfiguration](./Backup-WebConfiguration.md)

[Get-WebConfigurationBackup](./Get-WebConfigurationBackup.md)

