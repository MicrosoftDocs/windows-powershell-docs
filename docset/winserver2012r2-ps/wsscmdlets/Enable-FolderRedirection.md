---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Enable-FolderRedirection
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-12-05
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 23F24EA9-D61B-4DC7-8C28-2853AF4B2E2D
ms.author: v-anbarr
ms.reviewer: brianlic
---

# Enable-FolderRedirection

## SYNOPSIS
Enables the group policy setting for folder redirection.

## SYNTAX

### All
```
Enable-FolderRedirection [-AllFolder] [<CommonParameters>]
```

### Specific
```
Enable-FolderRedirection -Folder <String[]> [<CommonParameters>]
```

## DESCRIPTION
The **Enable-FolderRedirection** cmdlet enables the group policy setting for folder redirection.
This setting affects either all pre-defined folders or folders that you specify.
You can use folder redirection to redirect the path of a folder to a new location.

## EXAMPLES

### Example 1: Enable the group policy setting for folder redirection
```
PS C:\> Enable-FolderRedirection -Folder "Contacts","Videos"
```

This command enables the group policy for folder redirection for the contacts and video folders.

## PARAMETERS

### -AllFolder
Indicates that the group policy setting for folder redirection affects all pre-defined folders.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Folder
Specifies an array of folder names for which you want to enable the group policy setting for folder redirection.

```yaml
Type: String[]
Parameter Sets: Specific
Aliases: 
Accepted values: AppDataRoamingprivate, Contacts, Desktop, Documents, Downloads, Favorites, Links, Music, Pictures, SavedGames, Searches, StartMenu, Videos

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-FolderRedirection](./Disable-FolderRedirection.md)

