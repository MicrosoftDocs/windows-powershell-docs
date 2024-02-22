---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ShieldedVmCmdlets-help.xml
Module Name: ShieldedVMProvisioning
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/shieldedvmcmdlets/initialize-shieldedvm?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Initialize-ShieldedVM
---

# Initialize-ShieldedVM

## SYNOPSIS
Provisions a Shielded virtual machine.

## SYNTAX

### ByVM
```
Initialize-ShieldedVM [-ShieldingDataFilePath] <String> [[-ShieldedVMSpecializationDataFilePath] <String>]
 [-VM] <VirtualMachine> [<CommonParameters>]
```

### ByName
```
Initialize-ShieldedVM [-ShieldingDataFilePath] <String> [[-ShieldedVMSpecializationDataFilePath] <String>]
 [-VMName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Initialize-ShieldedVM** cmdlet provisions a shielded virtual machine.

## EXAMPLES

### Example 1: Provision a Shielded virtual machine
```
PS C:\>Initialize-ShieldedVM -ShieldingDataFilePath "C:\temp\Tenant01-Shielded.pdk" -ShieldedVMSpecializationDataFilePath "C:\temp\Tenant01-VM01.fsk" -VMName "VM01"
```

This command starts provisioning the virtual machine named VM01 on the local system using the shielding data file at C:\temp\Tenant01-Shielded.pdk and substituting values from the specialization file at C:\temp\Tenant01-VM01.fsk.

### Example 2: Provision a Shielded virtual machine that is stored in a variable
```
PS C:\>Initialize-ShieldedVM -ShieldingDataFilePath "C:\temp\Tenant01-Shielded.pdk" -ShieldedVMSpecializationDataFilePath "C:\temp\Tenant01-VM01.fsk" -VirtualMachine $VM
```

This command starts provisioning the virtual machine stored in the variable named $VM that uses the shielding data file at C:\temp\Tenant01-Shielded.pdk and substitutes values from the specialization file at C:\temp\Tenant01-VM01.fsk.

## PARAMETERS

### -ShieldedVMSpecializationDataFilePath
Specifies the location of a specialization data file (.fsk) used to substitute values in the specialization phase of the shielded virtual machine.

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

### -ShieldingDataFilePath
Specifies the location of a shielding data file (.pdk) used to configure and specialize the virtual machine.

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

### -VM
Specifies the virtual machine that this cmdlet provisions.

```yaml
Type: VirtualMachine
Parameter Sets: ByVM
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine that this cmdlet provisions.

```yaml
Type: String
Parameter Sets: ByName
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### CimInstance

This cmdlet returns a CimInstance object that represents the provisioning job for the shielded virtual machine.

## NOTES

## RELATED LINKS

[Get-KeyProtectorFromShieldingDataFile](./Get-KeyProtectorFromShieldingDataFile.md)

[Get-ShieldedVMProvisioningStatus](./Get-ShieldedVMProvisioningStatus.md)

[New-ShieldedVMSpecializationDataFile](./New-ShieldedVMSpecializationDataFile.md)

[Test-ShieldingDataApplicability](./Test-ShieldingDataApplicability.md)
