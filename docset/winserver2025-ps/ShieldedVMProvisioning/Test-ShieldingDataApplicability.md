---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ShieldedVmCmdlets-help.xml
Module Name: ShieldedVMProvisioning
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/shieldedvmcmdlets/test-shieldingdataapplicability?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ShieldingDataApplicability
---

# Test-ShieldingDataApplicability

## SYNOPSIS
Verifies a shielding data file can be used with a given volume signature catalog.

## SYNTAX

```
Test-ShieldingDataApplicability [-ShieldingDataFilePath] <String> [-VolumeSignatureCatalogPath] <String>
 [<CommonParameters>]
```

## DESCRIPTION
The **Test-ShieldingDataApplicability** cmdlet verifies a shielding data file can be used with a given volume signature catalog.

## EXAMPLES

### Example 1: Verify that a shielding data file can be used with a given volume signature catalog
```
PS C:\>Test-ShieldingDataApplicability -ShieldingDataFilePath "C:\temp\Tenant01-Shielded.pdk" -VolumeSignatureCatalogPath "C:\temp\templatedisk.vsc"
```

This command verifies that the shielding data file located at C:\temp\Tenant01-Shielded.pdk can be used to provision new shielded virtual machines using the template disk with the volume signature catalog located at C:\temp\templatedisk.vsc.

## PARAMETERS

### -ShieldingDataFilePath
Specifies the path to a shielding data file (.pdk).

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

### -VolumeSignatureCatalogPath
Specifies the path to a volume signature catalog file (.vsc).

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-KeyProtectorFromShieldingDataFile](./Get-KeyProtectorFromShieldingDataFile.md)

[Get-ShieldedVMProvisioningStatus](./Get-ShieldedVMProvisioningStatus.md)

[Initialize-ShieldedVM](./Initialize-ShieldedVM.md)

[New-ShieldedVMSpecializationDataFile](./New-ShieldedVMSpecializationDataFile.md)

