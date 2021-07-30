---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/disable-folderredirection?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-FolderRedirection
---

# Disable-FolderRedirection

## SYNOPSIS
Disables the group policy setting for folder redirection.

## SYNTAX

### All
```
Disable-FolderRedirection [-AllFolder] [<CommonParameters>]
```

### Specific
```
Disable-FolderRedirection -Folder <String[]> [<CommonParameters>]
```

## DESCRIPTION
The **Disable-FolderRedirection** cmdlet disables the group policy setting for folder redirection.
You can disable this setting either on all pre-defined folders or folders that you specify.

## EXAMPLES

### Example 1: Disable the group policy setting for folder redirection
```
PS C:\> Disable-FolderRedirection -Folder "Contacts","Videos"
```

This command disables the group policy setting for folder redirection for the contacts and video folders.

## PARAMETERS

### -AllFolder
Indicates that the cmdlet disables the group policy setting for folder redirection on all pre-defined folders.

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
Specifies an array of folder names for which you want to disable the group policy setting for folder redirection.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-FolderRedirection](./Enable-FolderRedirection.md)

