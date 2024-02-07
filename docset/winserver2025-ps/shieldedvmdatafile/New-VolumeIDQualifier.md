---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.HardenedFabric.Cmdlets.dll-Help.xml
Module Name: ShieldedVMDataFile
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/shieldedvmdatafile/new-volumeidqualifier?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-VolumeIDQualifier
---

# New-VolumeIDQualifier

## SYNOPSIS
Creates a volume ID qualifier.

## SYNTAX

### SignatureCatalog (Default)
```
New-VolumeIDQualifier [-VolumeSignatureCatalogFilePath] <String> [-VersionRule] <VolumeVersionRule>
 [<CommonParameters>]
```

### TemplateDisk
```
New-VolumeIDQualifier [-TemplateDiskFilePath] <String> [-VersionRule] <VolumeVersionRule> [<CommonParameters>]
```

## DESCRIPTION
The **New-VolumeIDQualifier** cmdlet creates a **VolumeIDQualifier** object from a volume signature catalog file and an associated rule.

## EXAMPLES

### Example 1: Create a volume ID qualifier
```
PS C:\>New-VolumeIDQualifier -VolumeSignatureCatalogFilePath "SignatureCatalog.vsc" -VolumeVersionRule Equals
```

This command creates a **VolumeIDQualifier** object that contains information associated with a .vsc file.
The **VolumeSignatureCatalogFilePath** parameter the .vsc file.

## PARAMETERS

### -TemplateDiskFilePath
The path to the template file.

```yaml
Type: String
Parameter Sets: TemplateDisk
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VersionRule
Specifies a rule that defines what volume versions the **VolumeIDQualifier** matches.
The acceptable values for this parameter are:

- Equals
- GreaterThan
- GreaterThanOrEquals

```yaml
Type: VolumeVersionRule
Parameter Sets: (All)
Aliases:
Accepted values: Equals, GreaterThan, GreaterThanOrEquals

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeSignatureCatalogFilePath
Specifies the path of a volume signature catalog file.
This type of file uses the .vsc file name extension.

```yaml
Type: String
Parameter Sets: SignatureCatalog
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String, VolumeVersionRule

## OUTPUTS

### VolumeIDQualifier
This object returns a new **VolumeIDQualifier** object.
Provide this object to the Protect-ShieldingDataFile to create a provisioning data file.

## NOTES

## RELATED LINKS

