---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/add-vmscsicontroller?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-VMScsiController

## SYNOPSIS
Adds a SCSI controller in a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-VMScsiController [-VMName] <String[]> [-ComputerName <String[]>] [-Passthru]
```

### UNNAMED_PARAMETER_SET_2
```
Add-VMScsiController [-VM] <VirtualMachine[]> [-Passthru]
```

## DESCRIPTION
The Add-VMScsiController cmdlet adds a SCSI controller in a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Add-VMScsiController -VMName TestVM
```

Adds a SCSI controller in virtual machine TestVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which a SCSI controller is to be added.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **VMScsiController** object is to be passed through to the pipeline representing the SCSI controller to be added.

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

### -VM
Specifies the virtual machine in which the SCSI controller is to be added.

```yaml
Type: VirtualMachine[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine in which the SCSI controller is to be added.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.Virtualization.Powershell.ScsiController
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



