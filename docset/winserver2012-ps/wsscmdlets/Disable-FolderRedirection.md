---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/disable-folderredirection?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Disable-FolderRedirection

## SYNOPSIS
Disables the group policy setting for folder redirection.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Disable-FolderRedirection [-AllFolder]
```

### UNNAMED_PARAMETER_SET_2
```
Disable-FolderRedirection -Folder <String[]>
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

[Enable-FolderRedirection](./Enable-FolderRedirection.md)

