---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.AppV.Modernizer.Cmdlets.dll-Help.xml
Module Name: AppvSequencer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/appvsequencer/expand-appvsequencerpackage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Expand-AppvSequencerPackage
---

# Expand-AppvSequencerPackage

## SYNOPSIS
Expands an existing App-V package.

## SYNTAX

```
Expand-AppvSequencerPackage [-AppvPackagePath] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Expand-AppvSequencerPackage** cmdlet expands a Microsoft Application Virtualization (App-V) package into its native form to the NTFS file system on the computer running the sequencer.
You can more easily add prerequisites or dependent applications to the sequencer before generating the package.

Run this cmdlet each time to expand a new package onto the computer running the sequencer.

## EXAMPLES

### Example 1: Expand a package
```
PS C:\> Expand-AppvSequencerPackage -AppvPackagePath "C:\MyPackages\PreReq.appv"
```

This command expands the package PreReq.appv to the sequencing computer.

## PARAMETERS

### -AppvPackagePath
Specifies the file path to an existing App-V package to be expanded to the NTFS file system of the computer running the cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AppvPackage

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AppvSequencerPackage](./New-AppvSequencerPackage.md)

[Update-AppvSequencerPackage](./Update-AppvSequencerPackage.md)

