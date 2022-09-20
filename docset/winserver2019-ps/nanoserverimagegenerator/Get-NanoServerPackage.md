---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NanoServerImageGenerator-help.xml
Module Name: NanoServerImageGenerator
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nanoserverimagegenerator/get-nanoserverpackage?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NanoServerPackage
---

# Get-NanoServerPackage

## SYNOPSIS
Gets available packages for a Nano Server installation image.

## SYNTAX

```
Get-NanoServerPackage [[-MediaPath] <String>] [[-BasePath] <String>] [[-LogPath] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NanoServerPackage** cmdlet gets packages that are available to embed into a Nano Server installation image.

## EXAMPLES

### Example 1: Get available packages
```
PS C:\> Get-NanoServerPackage -MediaPath D:\
```

This command gets packages available on the source media mounted on the D: drive.

## PARAMETERS

### -BasePath
Specifies the path to the source media.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogPath
Specifies the path where log files from the operation will be collected.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MediaPath
Specifies the path of the source media.
If a local copy of the source media already exists, and it is specified as the base path, then no copying is performed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS
### System.String

## NOTES

## RELATED LINKS

[Edit-NanoServerImage](./Edit-NanoServerImage.md)

[New-NanoServerImage](./New-NanoServerImage.md)

