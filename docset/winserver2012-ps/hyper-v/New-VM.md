---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/new-vm?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-VM

## SYNOPSIS
Creates a new virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-VM [[-Name] <String>] [[-MemoryStartupBytes] <Int64>] [-AsJob] [-BootDevice <BootDevice>]
 [-ComputerName <String[]>] [-NoVHD] [-Path <String>] [-SwitchName <String>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
New-VM [[-Name] <String>] [[-MemoryStartupBytes] <Int64>] [-AsJob] [-BootDevice <BootDevice>]
 [-ComputerName <String[]>] [-Path <String>] [-SwitchName <String>] -NewVHDPath <String>
 -NewVHDSizeBytes <UInt64> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
New-VM [[-Name] <String>] [[-MemoryStartupBytes] <Int64>] [-AsJob] [-BootDevice <BootDevice>]
 [-ComputerName <String[]>] [-Path <String>] [-SwitchName <String>] -VHDPath <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **New-VM** cmdlet creates a new virtual machine.

## EXAMPLES

### Example 1
```powershell
PS C:\>New-VM -Name "new 1" -MemoryStartupBytes 512MB
```

This example creates a new virtual machine named new 1 that has 512 MB of memory.

### Example 2
```powershell
PS C:\>New-VM -Name "new 2" -MemoryStartupBytes 1GB -NewVHDPath d:\vhd\base.vhdx -NewVHDSizeBytes 40GB
```

This example creates a virtual machine named new 2 that has 1 GB of memory and that is connected to a new 40 GB virtual hard disk that uses the VHDX format.

### Example 3
```powershell
PS C:\>New-VM -Name "new 3" -MemoryStartupBytes 1GB -VHDPath d:\vhd\BaseImage.vhdx
```

This example creates a virtual machine named new 3 that has 1 GB of memory and connects it to an existing virtual hard disk that uses the VHDX format.

### Example 4

```powershell
New-VM -Name "new 4" -MemoryStartupBytes 2GB -Credential (Get-Credential) -ComputerName HostServer01
```

This example asks for credentials, then creates a virtual machine named new 4, which has 2 GB of memory, on the server named HostServer01.

### Example 5

```powershell
New-VM -Name "new 5" -BootDevice CD -NoVHD
```

This example creates a virtual machine named new 5. The machine doesn't have any VHD disk and is set to boot from CD. 

### Example 6

```powershell
$oldVM = Get-VM "old 1"
$memory = (Get-VMMemory -VMName $oldVM.name).Startup
$switch = (Get-VMNetworkAdapter -VMName $oldVM.name).SwitchName
New-VM -Name "new 6" -MemoryStartupBytes $memory -SwitchName $switch
```

This example creates a virtual machine named new 6. The machine has the same amount of assigned memory as the existing machine named old 1 and connects to the same network switch.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.

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

### -BootDevice
Specifies the device to use as the boot device for the new virtual machine.
Allowed values are **CD**, **Floppy**, **LegacyNetworkAdapter**, and **IDE**.
When LegacyNetworkAdapter is specified, this configures the new virtual machine with a legacy network adapter (which can be used to perform a PXE boot and install an operating system from a network installation server.)

```yaml
Type: BootDevice
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual machine is to be created.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -MemoryStartupBytes
Specifies the amount of memory, in bytes, to assign to the virtual machine.
The default value is 512 MB.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the new virtual machine.
The default name is New virtual machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases: VMName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -NewVHDPath
Creates a new virtual hard disk with the specified path and connects it to the new virtual machine.
Absolute paths are allowed.
If only a file name is specified, the virtual hard disk is created in the default path configured for the host.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoVHD
Creates a virtual machine without attaching any virtual hard disks.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the directory to store the files for the new virtual machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SwitchName
Specifies the friendly name of the virtual switch if you want to connect the new virtual machine to an existing virtual switch to provide connectivity to a network.
Hyper-V automatically creates a virtual machine with one virtual network adapter, but connecting it to a virtual switch is optional.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VHDPath
Specifies the path to a virtual hard disk file.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewVHDSizeBytes
Specifies the size of the dynamic virtual hard disk that is created and attached to the new virtual machine.

```yaml
Type: UInt64
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### Microsoft.Virtualization.Powershell.VirtualMachine

## NOTES

## RELATED LINKS
