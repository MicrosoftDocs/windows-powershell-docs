---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Set-VMDvdDrive
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 403BB6A5-E31E-4256-9D10-1018E39B317E
---

# Set-VMDvdDrive

## SYNOPSIS
Configures a virtual DVD drive.

## SYNTAX

### VMName (Default)
```
Set-VMDvdDrive [-ComputerName <String[]>] [-VMName] <String> [[-ControllerNumber] <Int32>]
 [[-ControllerLocation] <Int32>] [-ToControllerNumber <Int32>] [-ToControllerLocation <Int32>]
 [[-Path] <String>] [-ResourcePoolName <String>] [-AllowUnverifiedPaths] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
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
PS C:\>Set-VMDvdDrive -VMName TestVM -Path .\WinBuild.iso
```

Configures the virtual DVD drive of virtual machine TestVM to use WinBuild.iso as its media.

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

### -ComputerName
Specifies one or more Hyper-V hosts on which the DVD drive is to be configured.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: 

Required: False
Position: Named
Default value: .
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
None by default; **Microsoft.HyperV.PowerShell.DvdDrive** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

