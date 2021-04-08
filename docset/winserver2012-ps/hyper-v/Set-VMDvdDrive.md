---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/set-vmdvddrive?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-VMDvdDrive

## SYNOPSIS
Configures a virtual DVD drive.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-VMDvdDrive [-VMName] <String> [[-ControllerNumber] <Int32>] [[-ControllerLocation] <Int32>]
 [[-Path] <String>] [-AllowUnverifiedPaths] [-ComputerName <String[]>] [-Passthru] [-ResourcePoolName <String>]
 [-ToControllerLocation <Int32>] [-ToControllerNumber <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Set-VMDvdDrive [-VMDvdDrive] <DvdDrive[]> [[-Path] <String>] [-AllowUnverifiedPaths] [-Passthru]
 [-ResourcePoolName <String>] [-ToControllerLocation <Int32>] [-ToControllerNumber <Int32>]
```

## DESCRIPTION
The **Set-VMDvdDrive** cmdlet configures the controller and location of a virtual DVD drive.

## EXAMPLES

### Example 1
```
PS C:\>Set-VMDvdDrive -VMName TestVM -Path .\Windows7.iso
```

Configures the virtual DVD drive of virtual machine TestVM to use Test.iso as its media.

### Example 2
```
PS C:\>Set-VMDvdDrive -VMName TestVM -ControllerNumber 1 -ControllerLocation 0 -Path $null
```

Configures the virtual DVD drive at IDE 1,0 of virtual machine TestVM to use no media.
(This ejects any existing media from the virtual DVD drive.)

### Example 3
```
PS C:\>Get-VMDvdDrive -VMName TestVM -ControllerNumber 1 -ControllerLocation 0 | Set-VMDvdDrive -ToControllerLocation 1
```

Moves virtual DVD drive from IDE 1,0 to IDE 1,1 on virtual machine TestVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the DVD drive is to be configured.
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

### -ControllerLocation
Specifies the IDE controller location of the DVD drives to be configured.
If not specified, DVD drives in all controller locations are configured.

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

### -ControllerNumber
Specifies the IDE controller of the DVD drives to be configured.
If not specified, DVD drives attached to all controllers are configured.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.Virtualization.Powershell.DvdDrive** object is to be passed through to the pipeline representing the virtual DVD drive to be configured.

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
Specifies the path to the ISO file or physical DVD drive that will serve as media for the virtual DVD drive.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ResourcePoolName
Specifies the friendly name of the ISO resource pool to which this DVD drive is to be associated.

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

### -VMDvdDrive
Specifies the virtual DVD drive to be configured.

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

### -ToControllerLocation
Specifies the controller location to which this virtual DVD drive should be moved.

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
Specifies the controller number to which this VMDvdDrive should be moved.

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

### -VMName
Specifies the name of the virtual machine on which the DVD drive is to be configured.

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

### Microsoft.Virtualization.Powershell.DvdDrive
If **-PassThru** is specified.

## NOTES

## RELATED LINKS



