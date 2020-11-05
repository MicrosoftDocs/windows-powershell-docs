---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 23F24EA9-D61B-4DC7-8C28-2853AF4B2E2D
manager: dansimp
---

# Enable-FolderRedirection

## SYNOPSIS
Enables the group policy setting for folder redirection.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Enable-FolderRedirection [-AllFolder]
```

### UNNAMED_PARAMETER_SET_2
```
Enable-FolderRedirection -Folder <String[]>
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-FolderRedirection](./Disable-FolderRedirection.md)

