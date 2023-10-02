---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/rename-vm?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Rename-VM

## SYNOPSIS
Renames a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Rename-VM [-Name] <String> [-NewName] <String> [-ComputerName <String[]>] [-Passthru]
```

### UNNAMED_PARAMETER_SET_2
```
Rename-VM [-VM] <VirtualMachine[]> [-NewName] <String> [-Passthru]
```

## DESCRIPTION
The **Rename-VM** cmdlet renames a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Rename-VM VM1 -NewName VM2
```

Renames virtual machine VM1 to VM2.

### Example 2
```
PS C:\>Get-VM VM1 | Rename-VM -NewName VM2 -PassThru
```

Renames virtual machine VM1 to VM2 and displays the renamed virtual machine.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual machine is to be deleted.
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

### -Name
Specifies the name of the virtual machine to be renamed.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -NewName
Specifies the name to which the virtual machine is to be renamed.

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

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the virtual machine to be renamed.

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
Specifies the virtual machine to be renamed.

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

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.Virtualization.Powershell.VirtualMachine
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



