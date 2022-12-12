---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmscsicontroller?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VMScsiController

## SYNOPSIS
Gets the SCSI controllers of a virtual machine or snapshot.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VMScsiController [-VMName] <String[]> [[-ControllerNumber] <Int32>] [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-VMScsiController [-VM] <VirtualMachine[]> [[-ControllerNumber] <Int32>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-VMScsiController [-VMSnapshot] <VMSnapshot> [[-ControllerNumber] <Int32>]
```

## DESCRIPTION
The **Get-VMScsiController** cmdlet gets the SCSI controllers of a virtual machine or snapshot.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMScsiController -VMName TestVM -ControllerNumber 0
```

Gets SCSI controller 0 from virtual machine TestVM.

### Example 2
```
PS C:\>Get-VM -Name TestVM -ComputerName Development | Get-VMScsiController
```

Gets the SCSI controllers from virtual machine TestVM on Hyper-V host Development.

### Example 3
```
PS C:\>Get-VMSnapshot -VMName TestVM -Name 'Before applying updates' | Get-VMScsiController
```

Gets the SCSI controllers from snapshot Before applying updates of virtual machine TestVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the SCSI controllers are to be retrieved.
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

### -ControllerNumber
Specifies the number of the SCSI controller to be retrieved.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine whose SCSI controllers are to be retrieved.

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
Specifies the name of the virtual machine whose SCSI controllers are to be retrieved.

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

### -VMSnapshot
Specifies the snapshot whose SCSI controllers are to be retrieved.

```yaml
Type: VMSnapshot
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Virtualization.Powershell.IDEController

## NOTES

## RELATED LINKS



