---
author: Kateyanne
description: 
external help file: WssCmdlets.dll-Help.xml
manager: jasgro
Module Name: WSSCmdlets
ms.author: v-kaunu
ms.date: 12/05/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/set-wssfilehistoryconfiguration?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WssFileHistoryConfiguration
---

# Set-WssFileHistoryConfiguration

## SYNOPSIS
Changes the File History configurations settings for the server.

## SYNTAX

```
Set-WssFileHistoryConfiguration [-Configuration] <ConfigurationSet> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssFileHistoryConfiguration** cmdlet changes the File History configuration settings for the server.
File History is a backup application that continuously protects the personal files of users stored in Libraries, Desktop, Favorites, and Contacts folders.
You can use the Get-WssFileHistoryConfiguration to get the File History configurations settings for the server.

## EXAMPLES

### Example 1: Change the File History configurations settings
```
PS C:\> $fileHistoryConfig = Get-WssFileHistoryConfiguration
PS C:\> $FileHistoryConfig.RetentionInMonths = 6
PS C:\> Set-WssFileHistoryConfiguration -Configuration $fileHistoryConfig
```

This example changes the File History configurations settings for the server.

The first command gets the File History configurations settings for the server, and stores the result in the **$fileHistoryConfig** variable.

The second command sets the RetentionInMonths property of the File History configurations object to six months.

The third command sets the File History configuration settings stored in **$fileHistoryConfig**.

## PARAMETERS

### -Configuration
Specifies the File History configuration settings for the server.

```yaml
Type: ConfigurationSet
Parameter Sets: (All)
Aliases: Config

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### -Force
Forces the command to run without asking for user confirmation.

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

### Microsoft.WindowsServerSolutions.DataProtection.FileBackup.ConfigurationSet

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.FileBackup.ConfigurationSet
This cmdlet generates the file history configuration settings stored on the server.

## NOTES

## RELATED LINKS

[Get-WssFileHistoryManagementStatus](./Get-WssFileHistoryManagementStatus.md)

