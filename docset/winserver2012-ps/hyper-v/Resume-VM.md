---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Resume-VM

## SYNOPSIS
Resumes a suspended (paused) virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Resume-VM [-Name] <String[]> [-AsJob] [-ComputerName <String[]>] [-Passthru]
```

### UNNAMED_PARAMETER_SET_2
```
Resume-VM [-VM] <VirtualMachine[]> [-AsJob] [-Passthru]
```

## DESCRIPTION
The **Resume-VM** cmdlet resumes a suspended (paused) virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Resume-VM -Name TestVM
```

Resumes suspended (paused) virtual machine TestVM.

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
Specifies one or more Hyper-V hosts on which the virtual machine is to be resumed.
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
Specifies the name of the virtual machine to be resumed.

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

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the virtual machine to be resumed.

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

### Microsoft.HyperV.Powershell.VirtualMachine
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



