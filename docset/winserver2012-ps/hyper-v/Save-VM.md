---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/save-vm?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Save-VM

## SYNOPSIS
Saves a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Save-VM [-Name] <String[]> [-AsJob] [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Save-VM [-VM] <VirtualMachine[]> [-AsJob]
```

## DESCRIPTION
The **Save-VM** cmdlet saves a virtual machine.
This is similar to hibernating a physical machine.

## EXAMPLES

### Example 1
```
PS C:\>Save-VM -Name TestVM
```

Saves virtual machine TestVM.

### Example 2
```
PS C:\>Get-VM -Name Win* | Save-VM
```

Saves all virtual machines whose name starts with Win.

## PARAMETERS

### -AsJob
Specifies that the cmdlet is to be run as a background job.

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

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual machine is to be saved.
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
Specifies the name of the virtual machine to be saved.

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

### -VM
Specifies the virtual machine to be saved.

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

## NOTES

## RELATED LINKS



