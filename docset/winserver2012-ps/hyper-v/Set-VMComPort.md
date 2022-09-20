---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vmcomport?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-VMComPort

## SYNOPSIS
Configures the COM port of a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-VMComPort [-VMName] <String[]> [-Number] <Int32> [-Path] <String> [-ComputerName <String[]>] [-Passthru]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-VMComPort [-VM] <VirtualMachine[]> [-Path] <String> [-Passthru] [-Number] <Int32> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Set-VMComPort [-VMComPort] <VMComPort[]> [-Path] <String> [-Passthru] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-VMComPort** cmdlet configures the COM port of a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Set-VMComPort TestVM 2 \\.\pipe\TestPipe
```

Configure the second COM port on virtual machine TestVM to connect to named pipe TestPipe on the local computer.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the COM port of a virtual machine is to be configured.
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

### -Number
Specifies the Id (1 or 2) of the COM port to be configured.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.Virtualization.Powershell.ComPort** object is to be passed through to the pipeline representing the COM port to be configured.

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

### -Path
Specifies a named pipe path for the COM port to be configured.
Specify local pipes as "\\\\.\pipe\PipeName" and remote pipes as "\\\\RemoteServer\pipe\PipeName".

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine for which the COM port is to be configured.

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

### -VMComPort
Specifies the COM port to be configured.

```yaml
Type: VMComPort[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine for which the COM port is to be configured.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.Virtualization.Powershell.ComPort
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



