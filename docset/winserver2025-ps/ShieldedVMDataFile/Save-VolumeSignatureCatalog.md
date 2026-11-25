---
external help file: Microsoft.Windows.HardenedFabric.Cmdlets.dll-Help.xml
Module Name: ShieldedVMDataFile
online version: https://learn.microsoft.com/powershell/module/shieldedvmdatafile/save-volumesignaturecatalog?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Save-VolumeSignatureCatalog
---

# Save-VolumeSignatureCatalog

## SYNOPSIS
Extracts and saves a volume signature catalog file from a given shielded VM template disk.

## SYNTAX

```
Save-VolumeSignatureCatalog [-TemplateDiskPath] <String> [-VolumeSignatureCatalogPath] <String>
```

## DESCRIPTION
The **Save-VolumeSignatureCatalog** cmdlet extracts the volume signature catalog containing the disk signer, name, and version number of a shielded VM template disk and persists it to a file.
This file can be given to VM owners who wish to deploy a VM using this template disk for use in the Shielding Data File Wizard.

## EXAMPLES

### Example 1
```
PS C:\> Save-VolumeSignatureCatalog -TemplateDiskPath 'C:\temp\mydisk.vhdx' -VolumeSignatureCatalogPath 'C:\temp\mydiskcatalog.vsc'
```

Saves the volume signature from the template disk to a file.

## PARAMETERS

### -TemplateDiskPath
Specifies the path to a VHDX file that has been templatized in preparation for deploying shielded VMs.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeSignatureCatalogPath
Specifies the desired path for the volume signature catalog file.
The path should use a .vsc extension.

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

## INPUTS

### None


## OUTPUTS

### None

## NOTES

## RELATED LINKS

