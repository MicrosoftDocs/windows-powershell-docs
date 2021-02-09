---
ms.technology: 
ms.mktglfcycl: manage
ms.author: v-kaunu
ms.prod: w10
ms.sitesec: library
author: Kateyanne
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: 29FA7DD2-3E1C-4B24-A963-BED8FC167EF9
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Restore-UevUserSetting
ms.reviewer:
---

# Restore-UevUserSetting

## SYNOPSIS
Sets a restore flag for the user settings.

## SYNTAX

### ParameterSetApplication
```
Restore-UevUserSetting [-Force] -Application <String> [-LastKnownGood] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ParameterSetTemplateId
```
Restore-UevUserSetting [-TemplateId] <String> [-LastKnownGood] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Restore-UevUserSetting cmdlet sets a restore flag for the user application settings or Windows operating system settings group.
You must perform this action for each application for which to restore the user settings.
The settings are restored the next time you run the application or log on to the operating system.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\>
Restore-UevUserSetting -TemplateId "MicrosoftCalculator6"
```

Description-----------This command sets a restore flag for the user settings that are identified by the template ID MicrosoftCalculator6.

### -------------------------- EXAMPLE 2 --------------------------
```
PS C:\>
Get-UevTemplate | Restore-UevUserSetting
```

Description-----------This command sets a restore flag for all user settings.

### -------------------------- EXAMPLE 3 --------------------------
```
PS C:\>
Restore-UevUserSetting -Application "word"

Confirm
The following user settings will be restored:

MicrosoftOffice2010.Word (Microsoft Office 2010.Word)
MicrosoftWordpad6 (Microsoft Wordpad)

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

Description-----------This command sets a restore flag for user settings for applications with names that contain the string word.

### -------------------------- EXAMPLE 4 --------------------------
```
PS C:\>
Restore-UevUserSetting -Application "office*word" -Force
```

Description-----------This command sets a restore flag for the user settings of the application whose name contains the strings office and word, in that order.

## PARAMETERS

### -Application
Specifies the name of an application.
Use the application name, or a partial name with wildcard characters, to set the restore flag for specific applications.

```yaml
Type: String
Parameter Sets: ParameterSetApplication
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to execute without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetApplication
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LastKnownGood
Restore the application to the settings last known good state.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemplateId
Specifies the ID of a template.
The cmdlet sets the restore flag for the application settings or operating system settings group to restore.

```yaml
Type: String
Parameter Sets: ParameterSetTemplateId
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

