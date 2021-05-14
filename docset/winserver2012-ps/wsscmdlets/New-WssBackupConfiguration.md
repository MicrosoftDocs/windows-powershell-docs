---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/new-wssbackupconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-WssBackupConfiguration

## SYNOPSIS
Creates a file specification that specifies the files and folders to include in or exclude from a backup.

## SYNTAX

```
New-WssBackupConfiguration [-FilePath] <String> [-FileName] <String> [-IsDirectory] [-IsExcludeSpec]
```

## DESCRIPTION
The **New-WssBackupConfiguration** cmdlet creates a file specification for a backup of a volume.
The file specification lists the files and folders to include in or exclude from the backup.

## EXAMPLES

### Example 1: Create a backup file specification
```
PS C:\> $Spec = New-WssBackupConfiguration -FilePath "c:\users\" -FileName * -IsDirectory -IsExcludeSpec
```

This command creates a backup file specification that excludes folders in the c:\users path from the backup.
It then stores the backup specification in the variable named $Spec.

## PARAMETERS

### -FileName
Specifies the name of a file to back up.
Use * for this parameter to back up all files in the path that the **FilePath** parameter specifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath
Specifies the path that contains the files to back up.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsDirectory
Indicates that the file specification refers to a folder.

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

### -IsExcludeSpec
Indicates that the cmdlet excludes the files in the specification from the backup

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WssBackupConfiguration](./Add-WssBackupConfiguration.md)

[Get-WssBackupConfiguration](./Get-WssBackupConfiguration.md)

[Remove-WssBackupConfiguration](./Remove-WssBackupConfiguration.md)

