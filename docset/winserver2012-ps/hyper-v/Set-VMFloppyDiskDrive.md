---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/set-vmfloppydiskdrive?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-VMFloppyDiskDrive

## SYNOPSIS
Configures a virtual floppy disk drive.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-VMFloppyDiskDrive [-VMName] <String[]> [[-Path] <String>] [-ComputerName <String[]>] [-Passthru]
 [-ResourcePoolName <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Set-VMFloppyDiskDrive [-VM] <VirtualMachine[]> [[-Path] <String>] [-Passthru] [-ResourcePoolName <String>]
```

### UNNAMED_PARAMETER_SET_3
```
Set-VMFloppyDiskDrive [-VMFloppyDiskDrive] <VMFloppyDiskDrive[]> [[-Path] <String>] [-Passthru]
 [-ResourcePoolName <String>]
```

## DESCRIPTION
The **Set-VMFloppyDiskDrive** cmdlet configures a virtual floppy disk drive.

## EXAMPLES

### Example 1
```
PS C:\>Set-VMFloppyDiskDrive TestVM C:\Test.vfd
```

Connect C:\Test.vfd to the virtual floppy disk of virtual machine TestVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual floppy disk drive is to be configured.
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
Specifies that a **Microsoft.Virtualization.Powershell.FloppyDiskDrive** object is to be passed through to the pipeline representing the virtual floppy disk drive to be configured.

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
Specifies the path to the virtual floppy drive file.
If specified as **$null**, the drive is set to contain no media.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ResourcePoolName
Specifies the name of the virtual floppy disk resource pool to use for this virtual floppy disk.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -VM
Specifies the virtual machine in which the virtual floppy disk drive is to be configured.

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

### -VMFloppyDiskDrive
Specifies the virtual floppy disk drive to be configured.

```yaml
Type: VMFloppyDiskDrive[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine on which the virtual floppy disk drive is to be configured.

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

## NOTES

## RELATED LINKS



