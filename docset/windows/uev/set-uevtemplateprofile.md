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
title: Set-UevTemplateProfile
ms.reviewer:
ms.assetid: 01231844-3E17-4BFE-B052-538DD8D755B2
---

# Set-UevTemplateProfile

## SYNOPSIS
Modifies which profile to associate with an individual template.

## SYNTAX

```
Set-UevTemplateProfile -ID <String> -Profile <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-UevTemplateProfile** cmdlet modifies which profile to associate with an individual template.
You can associate a template with the roaming profile or with the backup profile.
If you have not specified the profile for a template, the template associates to the roaming profile.

## EXAMPLES

### Example 1: Associate a template with the Backup profile
```
PS C:\>Set-UevTemplateProfile -ID "MicrosoftCalculator6" -Profile "Backup"
```

This command associates a template with the backup profile.
Settings for the application back-up, instead of synchronizing between computers.

### Example 2: Associate a template with the Roaming profile
```
PS C:\>Set-UevTemplateProfile -ID "MicrosoftCalculator6" -Profile "Roaming"
```

This command associates a template with the roaming profile.
Settings for the application synchronize between computers.

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

### -ID
Specifies the ID of a settings location template.
If you specify an ID for a template that is not registered, this cmdlet returns an error.

```yaml
Type: String
Parameter Sets: (All)
Aliases: TemplateID

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Specifies the name of a profile.
The cmdlet associates the template with the specified profile.
Valid values are: 

- Roaming
- Backup

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Roaming, Backup, Vdi

Required: True
Position: Named
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-UevTemplate](./Get-UevTemplate.md)

[Restore-UevBackup](./Restore-UevBackup.md)

