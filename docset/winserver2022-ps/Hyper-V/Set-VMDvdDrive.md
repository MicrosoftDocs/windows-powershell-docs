---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vmdvddrive?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VMDvdDrive
---

# Set-VMDvdDrive

## SYNOPSIS
Configures a virtual DVD drive.

## SYNTAX

### VMName (Default)
```
Set-VMDvdDrive [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String> [[-ControllerNumber] <Int32>] [[-ControllerLocation] <Int32>] [-ToControllerNumber <Int32>]
 [-ToControllerLocation <Int32>] [[-Path] <String>] [-ResourcePoolName <String>] [-AllowUnverifiedPaths]
 [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Object
```
Set-VMDvdDrive [-VMDvdDrive] <DvdDrive[]> [-ToControllerNumber <Int32>] [-ToControllerLocation <Int32>]
 [[-Path] <String>] [-ResourcePoolName <String>] [-AllowUnverifiedPaths] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMDvdDrive** cmdlet configures the controller and location of a virtual DVD drive.

## EXAMPLES

### Example 1
```
Set-VMDvdDrive -VMName TestVM -Path .\WinBuild.iso
```

Configures the virtual DVD drive of virtual machine TestVM to use WinBuild.iso as its media.

### Example 2
```
Set-VMDvdDrive -VMName TestVM -ControllerNumber 1 -ControllerLocation 0 -Path $null
```

Configures the virtual DVD drive at IDE 1,0 of virtual machine TestVM to use no media.
(This ejects any existing media from the virtual DVD drive.)

### Example 3
```
Get-VMDvdDrive -VMName TestVM -ControllerNumber 1 -ControllerLocation 0 | Set-VMDvdDrive -ToControllerLocation 1
```

Moves virtual DVD drive from IDE 1,0 to IDE 1,1 on virtual machine TestVM.

## PARAMETERS

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: VMName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the DVD drive is to be configured.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: 

Required: False
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
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerLocation
Specifies the IDE controller location of the DVD drives to be configured.
If not specified, DVD drives in all controller locations are configured.

```yaml
Type: Int32
Parameter Sets: VMName
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerNumber
Specifies the IDE controller of the DVD drives to be configured.
If not specified, DVD drives attached to all controllers are configured.

```yaml
Type: Int32
Parameter Sets: VMName
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: VMName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.HyperV.PowerShell.DvdDrive** object is to be passed through to the pipeline representing the virtual DVD drive to be configured.

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
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
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

### -VMDvdDrive
Specifies the virtual DVD drive to be configured.

```yaml
Type: DvdDrive[]
Parameter Sets: Object
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine on which the DVD drive is to be configured.

```yaml
Type: String
Parameter Sets: VMName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.HyperV.PowerShell.DvdDrive
If **-PassThru** is specified.

## NOTES

## RELATED LINKS

