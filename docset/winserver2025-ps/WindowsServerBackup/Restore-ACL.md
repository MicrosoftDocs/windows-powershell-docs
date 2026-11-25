---
description: The Restore-ACL cmdlet restores the security descriptor of a specified item, such as a file or a registry key.
external help file: wsbcmdlet.dll-help.xml
Module Name: WindowsServerBackup
ms.date: 09/10/2021
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/restore-acl?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-ACL
---

# Restore-ACL

## SYNOPSIS
Restores the security descriptor of a specified item.

## SYNTAX

```
Restore-ACL [-Path] <String> -XmlPath <String> -LogPath <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Restore-ACL** cmdlet restores the security descriptor of a specified item, such as a file or a registry key.

## EXAMPLES

### Example 1: Restore the ACL for a file
```powershell
Restore-ACL -Path  "C:\file01.txt" -XmlPath "C:\AclBackups\Backup-C-AclBackups-file01.txt-2021-11-02-02-14-11.xml" -LogPath "C:\AclBackupLogs\"
```

This command restores the ACL specified by the **XmlPath** parameter for the specified file.

## PARAMETERS

### -LogPath
Specifies the full path of the log file.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Path
Specifies the full path of the object for which the cmdlet restores permissions.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -XmlPath
Specifies the full path of the the XML file that contains ACL back up.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Backup-ACL](Backup-ACL.md)

[Get-ACL](/powershell/module/microsoft.powershell.security/get-acl)
