---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ShieldedVmCmdlets-help.xml
Module Name: ShieldedVMProvisioning
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/shieldedvmcmdlets/get-shieldedvmprovisioningstatus?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ShieldedVMProvisioningStatus
---

# Get-ShieldedVMProvisioningStatus

## SYNOPSIS
Queries the provisioning status of a shielded virtual machine.

## SYNTAX

### ByName (Default)
```
Get-ShieldedVMProvisioningStatus [-VMName] <String> [<CommonParameters>]
```

### ByVM
```
Get-ShieldedVMProvisioningStatus [-VM] <VirtualMachine> [<CommonParameters>]
```

### ByInstance
```
Get-ShieldedVMProvisioningStatus -ProvisioningJob <CimInstance> [<CommonParameters>]
```

## DESCRIPTION
The **Get-ShieldedVMProvisioningStatus** cmdlet queries the provisioning status of a shielded virtual machine.

## EXAMPLES

### Example 1: Get the provisioning job status for a virtual machine
```
PS C:\>Get-ShieldedVMProvisioningStatus -VMName "MyVM"
```

This command gets the provisioning job status for the virtual machine named MyVM.

### Example 2: Get the provisioning job status for a virtual machine using a variable
```
PS C:\>$VM = Get-VM -VMName "MyVM"
Get-ShieldedVMProvisioningStatus -VM $VM
```

The first command gets the virtual machine named MyVM and stores it in the variable named $VM.

The second command gets the provisioning job status for the virtual machine stored in the variable named $VM.

### Example 3: Get the provisioning job status for a virtual machine using an existing provisioning job object
```
PS C:\>$Job = Get-ShieldedVMProvisioningStatus -VMName "MyVM"
Get-ShieldedVMProvisioningStatus -ProvisioningJob $Job
```

The first command gets the provisioning job status for the virtual machine named MyVM and stores it in the variable named $Job.

The second command calls **Get-ShieldedVMProvisioningStatus** again using the provisioning job status stored in the $Job variable.

## PARAMETERS

### -ProvisioningJob
Specifies a **CimInstance** object returned from either the Initialize-ShieldedVM cmdlet or a prior call to the Get-ShieldedVMProvisioningStatus cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByInstance
Aliases:

Required: True
Position: Named
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
Position: 1
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
Position: 1
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

[Initialize-ShieldedVM](./Initialize-ShieldedVM.md)

[New-ShieldedVMSpecializationDataFile](./New-ShieldedVMSpecializationDataFile.md)

[Test-ShieldingDataApplicability](./Test-ShieldingDataApplicability.md)

