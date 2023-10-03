---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/export-vm?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Export-VM

## SYNOPSIS
Exports a virtual machine to disk.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Export-VM [-Name] <String[]> [-Path] <String> [-AsJob] [-ComputerName <String[]>] [-Passthru]
```

### UNNAMED_PARAMETER_SET_2
```
Export-VM [-VM] <VirtualMachine[]> [-Path] <String> [-AsJob] [-Passthru]
```

## DESCRIPTION
The **Export-VM** cmdlet exports a virtual machine to disk.
This cmdlet creates a folder at a specified location having three subfolders: Snapshots, Virtual Hard Disks, and Virtual Machines.
Each of these folders contains the associated files. The Snapshots folder contains the associated Snapshots, and the Virtual Hard Disk folder contains the specified virtual machine's virtual disks.
The Virtual Machines folder contains the configuration XML of the specified virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Export-VM -Name Test -Path D:\
```

Exports virtual machine Test to the root of the D drive.

### Example 2
```
PS C:\>Get-VM | Export-VM -Path D:\
```

Exports all virtual machines to the root of the D drive.
Each virtual machine will be exported to its own folder.

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
Specifies one or more Hyper-V hosts on which the virtual machine is to be exported.
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
Specifies the name of the virtual machine to be exported.

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
Specifies that a **Microsoft.Virtualization.Powershell.VirtualMachine** object is to be passed through to the pipeline representing the virtual machine to be exported.

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
Specifies the path to the folder into which the virtual machine is to be exported.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -VM
Specifies the virtual machine to be exported.

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



