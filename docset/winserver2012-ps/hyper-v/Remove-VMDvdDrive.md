---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/remove-vmdvddrive?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-VMDvdDrive

## SYNOPSIS
Deletes a DVD drive from a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-VMDvdDrive [-VMName] <String> [-ControllerNumber] <Int32> [-ControllerLocation] <Int32>
 [-ComputerName <String[]>] [-Passthru]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-VMDvdDrive [-VMDvdDrive] <DvdDrive[]> [-Passthru]
```

## DESCRIPTION
The **Remove-VMDvdDrive** cmdlet deletes a DVD drive from a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Remove-VMDvdDrive -VMName TestVM -ControllerNumber 1 -ControllerLocation 0
```

Removes the virtual DVD drive at IDE 1,0 on virtual machine TestVM.

### Example 2
```
PS C:\>Get-VMDvdDrive -VMName TestVM -ControllerNumber 1 | Remove-VMDvdDrive
```

Removes all virtual DVD drives on IDE controller 1 of virtual machine TestVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts from which the DVD drive is to be deleted.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the DVD drive to be deleted.

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

### -VMDvdDrive
Specifies the DVD drive to be deleted.

```yaml
Type: DvdDrive[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ControllerLocation
Specifies the number of the location on the controller at which the DVD drive is to be deleted.
If not specified, the number of the first available location on the controller is used.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerNumber
Specifies the number of the controller from which the DVD drive is to be deleted.
If not specified, the first IDE controller on which the specified **ControllerLocation** is available is used.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine from which the DVD drive is to be deleted.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.Virtualization.Powershell.DriveController
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



