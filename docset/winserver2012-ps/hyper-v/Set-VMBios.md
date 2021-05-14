---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/set-vmbios?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-VMBios

## SYNOPSIS
Configures the BIOS of a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-VMBios [-VMName] <String[]> [-ComputerName <String[]>] [-DisableNumLock] [-EnableNumLock] [-Passthru]
 [-StartupOrder <BootDevice[]>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-VMBios [-VM] <VirtualMachine[]> [-DisableNumLock] [-EnableNumLock] [-Passthru]
 [-StartupOrder <BootDevice[]>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Set-VMBios [-VMBios] <VMBios[]> [-DisableNumLock] [-EnableNumLock] [-Passthru] [-StartupOrder <BootDevice[]>]
 [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-VMBios** cmdlet configures the BIOS of a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\> Set-VMBios TestVM -DisableNumLock
```

This example disables the NumLock key by default on virtual machine TestVM.

### Example 2
```
PS C:\> Set-VMBios TestVM -StartupOrder @("Floppy", "LegacyNetworkAdapter", "CD", "IDE")
```

This example configures virtual machine TestVM to check for a boot device in the following order: floppy disk, network, CD drive, hard disk.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts for which the BIOS is to be configured.
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

### -DisableNumLock
Specifies that NumLock is to be disabled in the BIOS of the virtual machine to be configured.

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

### -EnableNumLock
Specifies that NumLock is to be enabled in the BIOS of the virtual machine to be configured.

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

### -Passthru
Specifies that an **Microsoft.Virtualization.Powershell.Bios** object is to be passed through to the pipeline representing the BIOS to be configured.

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

### -StartupOrder
Specifies an array of boot devices representing the boot order in the BIOS of the virtual machine.
The boot devices are specified as members of the **BootDevices** enumeration (**CD**, **IDE**, **LegacyNetworkAdapter**, **Floppy**).

```yaml
Type: BootDevice[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine for which the BIOS is to be configured.

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

### -VMBios
```yaml
Type: VMBios[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine for which the BIOS is to be configured.

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

### Microsoft.Virtualization.Powershell.Bios
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



