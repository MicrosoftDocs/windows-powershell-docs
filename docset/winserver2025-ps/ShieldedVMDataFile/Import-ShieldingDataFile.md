---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.HardenedFabric.Cmdlets.dll-Help.xml
Module Name: ShieldedVMDataFile
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/shieldedvmdatafile/import-shieldingdatafile?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-ShieldingDataFile
---

# Import-ShieldingDataFile

## SYNOPSIS
Imports shielding data.

## SYNTAX

```
Import-ShieldingDataFile [-ShieldingDataFilePath] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Import-ShieldingDataFile** cmdlet imports a **ShieldingDataFile** object from a shielding data file.

## EXAMPLES

### Example 1: Provision a virtual machine by using an imported data file
```
PS C:\>Import-ShieldingDataFile -ShieldingDataFilePath "ShieldingFile02.pdk" | Protect-ShieldingDataFile -ShieldingDataFilePath "ShieldingDataFile07.pdk"
```

This command creates a **ShieldingDataFile** object.
The command passes it to the Protect-ShieldingDataFile cmdlet.
That cmdlet specifies the output file name.

## PARAMETERS

### -ShieldingDataFilePath
Specifies the path of a shielding data file.
The file has the .pdk file name extension.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### ShieldingDataFile, ExistingVMShieldingDataFile
This cmdlet returns a **ShieldingDataFile** object.
This object represents a .pdk file used to provision a shielded virtual machine.

## NOTES

## RELATED LINKS

