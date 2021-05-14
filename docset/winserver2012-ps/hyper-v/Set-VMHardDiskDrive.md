---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://docs.microsoft.com/powershell/module/hyper-v/set-vmharddiskdrive?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-VMHardDiskDrive

## SYNOPSIS
Configures a virtual hard disk.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-VMHardDiskDrive [-VMName] <String> [[-ControllerType] <ControllerType>] [[-ControllerNumber] <Int32>]
 [[-ControllerLocation] <Int32>] [[-Path] <String>] [-AllowUnverifiedPaths] [-ComputerName <String[]>]
 [-DiskNumber <UInt32>] [-Passthru] [-ResourcePoolName <String>] [-ToControllerLocation <Int32>]
 [-ToControllerNumber <Int32>] [-ToControllerType <ControllerType>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-VMHardDiskDrive [-VMHardDiskDrive] <HardDiskDrive[]> [[-Path] <String>] [-AllowUnverifiedPaths]
 [-ComputerName <String[]>] [-DiskNumber <UInt32>] [-Passthru] [-ResourcePoolName <String>]
 [-ToControllerLocation <Int32>] [-ToControllerNumber <Int32>] [-ToControllerType <ControllerType>] [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Set-VMHardDiskDrive** cmdlet configures a virtual hard disk.

## EXAMPLES

### Example 1
```
PS C:\>Set-VMHardDiskDrive -VMName TestVM -Path .\Test.vhd
```

Configures the hard drive of virtual machine TestVM to use Test.vhd as its media.

### Example 2
```
PS C:\>Get-VMHardDiskDrive -VMName TestVM -ControllerType IDE -ControllerNumber 1 -ControllerLocation 0 | Set-VMHardDiskDrive -ToControllerLocation 1
```

Moves the virtual hard drive on virtual machine TestVM from IDE 1,0 to IDE 1,1.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual hard drive is to be configured.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: PSComputerName

Required: False
Position: Named
Default value: .
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ControllerLocation
Specifies the number of the location on the controller to which the virtual hard drive to be configured is attached.
If not specified, all hard drives are configured.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerNumber
Specifies the number of the controller to which the virtual hard drive to be configured is attached.
If not specified, all hard drives are configured.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerType
Specifies the type of the controller to which the virtual hard drive to be configured is attached.
Allowed values are **IDE** and **SCSI**.

```yaml
Type: ControllerType
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.Virtualization.Powershell.HardDiskDrive** object is to be passed through to the pipeline representing the virtual hard drive to be configured.

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
Specifies the path to media the virtual hard disk is to use.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourcePoolName
Specifies the name of the virtual hard disk resource pool to which this drive belongs.

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

### -VMHardDiskDrive
Specifies one or more hard disks to be configured.

```yaml
Type: HardDiskDrive[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AllowUnverifiedPaths
Specifies that no error is to be thrown if the specified path is not verified as accessible by the cluster.
This parameter is applicable to clustered virtual machines.

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

### -DiskNumber
Specifies the disk number of the offline physical hard drive that should be connected as a passthrough disk.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: Number

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ToControllerLocation
Specifies the controller location to which this drive should be moved.
Allowed values are 0 and 1 for IDE controllers, and from 0 to 63 for SCSI controllers.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ToControllerNumber
Specifies the controller location to which this drive should be moved.
Allowed values are 0 and 1 for IDE controllers, and from 0 to 3 for SCSI controllers.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ToControllerType
Specifies the type of controller to which this drive should be moved.
Allowed values are IDE and SCSI.

```yaml
Type: ControllerType
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine on which the virtual hard drive is to be configured.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
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

## NOTES

## RELATED LINKS



