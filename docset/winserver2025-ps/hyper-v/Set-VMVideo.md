---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vmvideo?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VMVideo
---

# Set-VMVideo

## SYNOPSIS
Configures video settings for virtual machines.

## SYNTAX

### VMName (Default)
```
Set-VMVideo [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String[]> [[-ResolutionType] <ResolutionType>] [[-HorizontalResolution] <UInt16>]
 [[-VerticalResolution] <UInt16>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Set-VMVideo [-VM] <VirtualMachine[]> [[-ResolutionType] <ResolutionType>] [[-HorizontalResolution] <UInt16>]
 [[-VerticalResolution] <UInt16>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMVideo
```
Set-VMVideo [-VMVideo] <VMVideo[]> [[-ResolutionType] <ResolutionType>] [[-HorizontalResolution] <UInt16>]
 [[-VerticalResolution] <UInt16>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMVideo** cmdlet configures the video settings for virtual machines.

## EXAMPLES

### Example 1: Set resolution for a virtual machine display
```
PS C:\> Set-VMVideo -VMName "VM06" -HorizontalResolution 1920 -VerticalResolution 1200
```

This command sets the video resolution for the virtual machine named VM06 to 1920x1200.

## PARAMETERS

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
Specifies one or more Hyper-V hosts that run this cmdlet.
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

### -HorizontalResolution
Specifies the horizontal resolution for the virtual machine display.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Indicates that this cmdlet returns the **Microsoft.HyperV.PowerShell.VMVideo** object that it modifies.

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

### -ResolutionType
Specifies the resolution type for the virtual machine display.
The acceptable values for this parameter are:

- Maximum.
The input HorizontalResolution * VerticalResolution is the maximum supported resolution.
All standard resolutions smaller than HorizontalResolution * VerticalResolution are also supported.
- Single.
The input HorizontalResolution * VerticalResolution is the only supported resolution.
- Default.
The supported resolutions are those in the list of standard resolutions.
Input HorizontalResolution * VerticalResolution is ignored.

```yaml
Type: ResolutionType
Parameter Sets: (All)
Aliases:
Accepted values: Maximum, Single, Default

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies an array of virtual machines for which this cmdlet configures video settings.
To obtain a **VirtualMachine** object, use the **Get-VM** cmdlet.

```yaml
Type: VirtualMachine[]
Parameter Sets: VMObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies an array of names of virtual machines for which this cmdlet configures video settings.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMVideo
Specifies an array of virtual machine video settings that this cmdlet configures.
To obtain a **VMVideo** object, use the **Get-VMVideo** cmdlet.

```yaml
Type: VMVideo[]
Parameter Sets: VMVideo
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VerticalResolution
Specifies the vertical resolution for the virtual machine display.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
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

### Microsoft.HyperV.PowerShell.VMVideo
This cmdlet returns a **VirtualMachine** object, if you specify the **Passthru** parameter.

## NOTES

## RELATED LINKS

[Get-VMVideo](./Get-VMVideo.md)

[Get-VM](./Get-VM.md)

