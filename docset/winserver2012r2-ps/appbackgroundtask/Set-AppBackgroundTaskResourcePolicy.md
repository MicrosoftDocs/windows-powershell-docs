---
external help file: microsoft.windows.appbackgroundtask.commands.dll-Help.xml
Module Name: AppBackgroundTask
online version: 
schema: 2.0.0
title: Set-AppBackgroundTaskResourcePolicy
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 82B0732A-B6CD-46C8-9D83-212A05EFB3D6
---

# Set-AppBackgroundTaskResourcePolicy

## SYNOPSIS
Configures the use of global pool by background tasks.

## SYNTAX

```
Set-AppBackgroundTaskResourcePolicy -Mode <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AppBackgroundTaskResourcePolicy** cmdlet configures the use of global pool by background tasks.
Global pool is a shared resource that provides CPU or network resources when an application needs additional resources to complete a task.
You must have administrator access to set the background task resource policy.

## EXAMPLES

### Example 1: Set global resource policy to conservative mode
```
PS C:\> Set-AppBackgroundTaskResourcePolicy -Mode Conservative
```

This command sets the global resource policy for background tasks to Conservative, which ensures that background tasks use the minimum CPU.

### Example 2: Set global resource policy to normal mode
```
PS C:\>Set-AppBackgroundTaskResourcePolicy -Mode Normal
```

This command sets the global resource policy for background tasks to Normal.
A restart is required if the previous setting was Conservative.

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

### -Mode
Specifies the global pool settings for background tasks on the system.
Acceptable values for this parameter are: Normal and Conservative.
Use Normal to enable the global pool for all applications.
Use Conservative to disable the global pool for all applications.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Normal, Conservative

Required: True
Position: Named
Default value: None
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS


